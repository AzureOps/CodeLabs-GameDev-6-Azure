﻿<a name="HOLTop"></a>
# Engaging Players with Azure #

---

<a name="Overview"></a>
## Overview ##

Enable your game with the Azure cloud services. Microsoft Azure offers hundreds of cross-platform services for any device: Android, iOS and Windows. In this module, you will use a sample game, create a new Azure App Service in Azure portal and add it to your game to save game score in the cloud. Naturally, your app can take advantage of multiple services available in Azure: you can choose what services to use in your game to expand it to its full potential. In this module, we use Azure App Service and SQL Azure backend to save your score.

<a name="Objectives"></a>
### Objectives ###
In this module, you will see how to:

- Connect your Unity game to Microsoft Azure
- Use Microsoft Azure App Service in your game
- Store game score using Azure

<a name="Prerequisites"></a>
### Prerequisites ###

The following is required to complete this module:

- Windows 10.
- [Visual Studio Community 2015][1] or greater.
- [Unity 5.3.3][2]

[1]: https://www.visualstudio.com/products/visual-studio-community-vs
[2]: http://www.unity3d.com

> **Note:** You can take advantage of the [Visual Studio Dev Essentials]( https://www.visualstudio.com/en-us/products/visual-studio-dev-essentials-vs.aspx) subscription in order to get everything you need to build and deploy your app on any platform.

<a name="Intended Audience"></a>
### Intended Audience ###

This module is intended for developer’s familiar with C# and Visual Studio. It does not require prior experience with Unity gaming platform.

---

<a name="Exercises"></a>
## Exercises ##
This module includes the following exercises:

1. [Create Azure App Service for your game](#Exercise1)
2. [Save game score in Azure App Service](#Exercise2)

Estimated time to complete this module: **60 minutes**

<a name="Exercise1"></a>
### Exercise 1: Create Azure App Service for your game ###

Most games need to save score and settings. Wouldn’t it be great if we can save user game score on one device, say a PC, and then when the user comes back to another device: his/her tablet or phone, the score is there? In this module, you’ll be able to do it and learn how to use Microsoft Azure portal.

For the purpose of this module, we use a popular Unity Tanks! tutorial game available from Unity3D Web site. Tanks! is a very nice [multiplayer game example](http://unity3d.com/learn/tutorials/projects/tanks-tutorial). In this code module, you’ll learn how to modify this game to add Azure functionality to the game.

![Tanks Game](Images/tanks-game.png?raw=true "Tanks Game")

_Tanks Game_

<a name="Ex1Task1"></a>
#### Task 1 - Create Azure Mobile App ####

Microsoft Azure provides hundreds of features game developers can take advantage of. One of them is Mobile Apps.

1. If you already have an Azure account go to [Azure Portal](http://portal.azure.com) or you can open a free one-month trial [Free Azure One-Month Trial](https://azure.microsoft.com/en-us/pricing/free-trial/). Inside of the Azure portal, simply select **New | Web + Mobile | Mobile App**, which is the starting point to configure your Azure Mobile App backend.

	![Create Azure Mobile App](Images/azure-create-mobile-app.png?raw=true "Create Azure Mobile App")

	_Create Azure Mobile App_

2. You’ll need to provide App Service name (this is the URL where your backend will live), configure your subscription, and set your resource group and plan. You can choose location where your app to be most active.

	![Configure Azure Mobile App](Images/azure-create-mobile-app-details.png?raw=true "Configure Azure Mobile App")

	_Configure Azure Mobile App_

3. Once deployed, the Azure portal will bring you directly to the configuration screen with the settings tab open. All of the settings we’ll adjust can be found under the Mobile section.

	![Configure Azure Settings](Images/azure-settings.png?raw=true "Configure Azure Settings")

	_Configure Azure Settings_

4. Our backend data will live in a database. Under the **Data Connections** section, select **Add**, and then configure a new SQL database.

	![Configure Azure Database Settings](Images/azure-db.png?raw=true "Configure Azure Database Settings")

	_Configure Azure Database Settings_

5. When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database. Click **OK** on all open blades and Azure will begin to create the database for us on the fly. When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database.

	![Azure Database Connection](Images/azure-db-connection.png?raw=true "Azure Database Connection")

	_Azure Database Connection_

6. Under Mobile settings is a new section called Easy Tables, which enable us to easily set up and control the data coming to and from the iOS and Android apps. Select the **Easy Tables** section, and we’ll be prompted with a big blue warning asking us to configure Easy Tables/Easy APIs.

	![Azure Easy Tables](Images/azure-easy-tables.png?raw=true "Azure Easy Tables")

	_Azure Easy Tables_

7. Since we already setup the database, the only thing left to do is Initialize the app.

	![Azure Initialize the App](Images/azure-init-app.png?raw=true "Azure Initialize the App")

	_Azure Initialize the App_

8. When the app will be fully initialized you can add our first table of the database named GameScore. If you are adding Azure Mobile Apps to an existing application, this table name should match the class name of the data you with to store. The beautiful part of Easy Tables is that it will automatically update and add the columns in the table dynamically based on the data we pass in. For this example, I’ll simply allow full anonymous access to the table, however it is possible to add authentication with Facebook, Twitter, Google, Microsoft, and other OAuth login providers.

	![Azure Add GameScore table](Images/azure-add-gamescore-table.png?raw=true "Azure Add GameScore table")

	_Azure Add GameScore table_

<a name="Exercise2"></a>
### Exercise 2: Save game settings and score in Azure ###

<a name="Ex2Task1"></a>
#### Task 1 - Open Game Project in Visual Studio ####

1. Launch **Unity** from the **Start Menu**, click **Open**. In the **Select Existing Unity Project** dialog navigate to **Ex2/Begin/UnityTanksWithAzure** and click **Select Folder**. Unity will import your project.

	![Open Unity Project](Images/create-open-existing-folder.png?raw=true "Open Unity Project")

	_Open Unity Project_

1. Next, you need to create a Windows UWP Universal Project from Unity. In Unity top menu select **File | Build Settings**, select **Windows Store**, make sure that SDK combo box has **Universal 10** selected, and checkboxes **Unity C# Projects** and **Development Build** are checked. Then click **Build**. In the following dialog box Unity prompts you to select a target folder where it'll place Visual Studio Windows 10 project. Select **Ex2\Begin\UnityTanksWithAzure\Ex2Begin** folder.

	![Generate UWP Project](Images/create-uwp-project.png?raw=true "Generate UWP Project")

	_Generate UWP Project_

1. Launch Visual Studio 2015 from the Start Menu. Then, open **UnityTanksWithAzure** solution that was generated in the previous step in **Ex2\Begin\UnityTanksWithAzure\Ex2Begin** by double clicking on it. Right click **UnityTanksWithAzure (Universal Windows)** project and select **Rebuild All**. After Visual Studio rebuilds the project you can run the project by pressing **F5**. This should start Tanks! game as a Windows Universal app.

	![Visual Studio Solution](Images/vs-solution.png?raw=true "Visual Studio Solution")

	_Visual Studio Solution_

> **Note:** At any point if you want to jump to the finished app, you can repeat steps in this task to generate a Ex2\End project, it contains completed source code.

<a name="Ex2Task2"></a>
#### Task 2 - Add code to save game score in Azure ####

1. First you need to create a data model for Azure Mobile app. The great thing about Azure Mobile apps is that as you change your data model, backend automatically picks up the changes. In our game we’ll save user and the best score achieved during the game. Add the following code to **GameScore.cs** file in **Assets\Complete\Scripts\Build16** folder.

	(Code Snippet - _GameAzure - Ex2 - GameScore.cs_)
	<!--mark: 1-10-->
	````C#
    public class GameScore
    {
        public string id { get; set; }

        public string user { get; set; }

        public float score { get; set; }

        public int tank { get; set; }
    }
	````

1. Next, you need to connect your game to Azure. Add the following code to **GameManager.cs** **Start** method after `//BUILD16 Connect to Azure` comment. Please, make sure to replace `<YOUR APP SERVICE>` with the name of the service you created in Azure portal.

	(Code Snippet - _GameAzure - Ex2 - ConnectToAzure_)
	<!--mark: 2-3-->
	````C#
	//BUILD16 Connect to Azure
	Debug.Log("Logging into Azure...");
	AzureMobileServices.Connect("https://<YOUR APP SERVICE>.azurewebsites.net");
	````

1. Next, add the following code right after that, this will save initial score to Azure.

	(Code Snippet - _GameAzure - Ex2 - InitialGameScore_)
	<!--mark: 1-15-->
	````C#
	//BUILD16 Save initial game score in Azure
	userId = System.Guid.NewGuid().ToString();
	GameScore score = new GameScore { user = userId, score = 0 };
	AzureMobileServices.Insert<GameScore>(score, (response) =>
	{
		if (response.Status == CallbackStatus.Failure)
		{
			 Debug.LogError("Inserting record failed.");
			 Debug.LogError(response.Exception.ToString());
			 return;
		}

		// print something
		Debug.Log("Successfully inserted item " + score.id);
	});
	````

1. Each time a tank wins a round, you need to save game score in Azure App Service for that tank. You need to add this method to **GameManager.cs**. This method checks if there's a winning tank **m_RoundWinner** and saves the score for that tank in the database.

	(Code Snippet - _GameAzure - Ex2 - SaveScoreInAzure_)
	<!--mark: 1-19-->
	````C#
	private void SaveScoreInAzure()
	{
		if (m_RoundWinner != null)
		{
			 GameScore score = new GameScore { user = userId, tank = m_RoundWinner.m_PlayerNumber, score = m_RoundWinner.m_Wins };
			 AzureMobileServices.Insert<GameScore>(score, (response) =>
			 {
				  if (response.Status == CallbackStatus.Failure)
				  {
						Debug.LogError("Inserting record failed.");
						Debug.LogError(response.Exception.ToString());
						return;
				  }

			 // print something
			 Debug.Log("Successfully inserted item " + score.id);
			 });
		}
	}
	````

1. Lastly, you need to invoke this method each time a round ends. Go to **GameManager.cs**, find **RoundEnding** method and add a call to your **SaveScoreToAzure()** method right below where the number of wins is incremented for the player. Don't forget to put both statements in curved brackets, like so.

	(Code Snippet - _GameAzure - Ex2 - RoundEndUpdate_)
	<!--mark: 1-6-->
	````C#
	// If there is a winner, increment their score.
	if (m_RoundWinner != null)
	{
		m_RoundWinner.m_Wins++;
		SaveScoreInAzure();
	}
	````

1. In Visual Studio you can fully debug your Unity game. Let's set a few breakpoints: in Visual Studio solution explorer navigate to **GameManager.cs**.

	![Set Breakpoints](Images/debug-project.png?raw=true "Set Breakpoints")

	_Set Breakpoints_

1. Set up a breakpoint before you call **AzureMobileServices.Insert** method.

	![Set Breakpoints for Score](Images/debug-save-score.png?raw=true "Set Breakpoints for Score")

	_Set Breakpoints for Score_

1. Now, build and run the game by pressing **F5** in Visual Studio. After the app launches, you can see that the GameScore table you’ve just created has a new record. In **Azure portal** click the **Game Score** table.

	![Game Score Inserted](Images/azure-table-insert.png?raw=true "Game Score Inserted")

	_Game Score Inserted_

1. Observe a new record added, or alternatively you can connect to the database directly from Visual Studio and check that records are inserted.

	![Game Score Inserted Record](Images/azure-insert-details.png?raw=true "Game Score Inserted Record")

	_Game Score Inserted Record_

---

<a name="Summary"></a>
## Summary ##

Congratulations on completing this module! You’ve learned how you can connect Microsoft Azure to your game with just a few lines of code. You learned how to use Microsoft Azure portal to create an manage Azure services. By completing this module, you should have:

- Created a Mobile App in Azure and connected to your game.
- Learned how to save game score in Azure

<a name="Additional Resources"></a>
## Additional Resources ##

- [Microsoft Azure](http://azure.microsoft.com)
- [Azure App Service](https://azure.microsoft.com/en-us/documentation/services/app-service/)
- [Unity Tanks Game](http://unity3d.com/learn/tutorials/projects/tanks-tutorial)
