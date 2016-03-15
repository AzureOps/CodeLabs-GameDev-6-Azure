<a name="Exercise1" />
### Exercise 1: Create Azure App Service for your game ###

Most games need to save score and settings. Wouldn’t it be great if we can save user game score on one device, say a PC and then when the user comes back to another device: his/her tablet or phone, the score is there? In this lab you’ll be able to do it and learn how to use Microsoft Azure portal.

For the purpose of this lab we use a popular Unity Tanks! tutorial game available from Unity3D Web site. Tanks! is a very nice [multiplayer game example](http://unity3d.com/learn/tutorials/projects/tanks-tutorial). In this code lab you’ll learn how to modify this game to add Azure functionality to the game. At any moment you can access any step of this tutorial in code. Simply look at the project folder

- TaskComplete folder contains complete code of the game
- TaskGameScore source of the game with game score added
 
![Tanks Game](Images/tanks-game.png?raw=true "Tanks Game")

<a name="Ex1Task1" />
#### Task 1 - Create Azure Mobile App ####

Microsoft Azure provides hundreds of features game developers can take advantage of. One of them is Mobile Apps. 

1. If you already have an Azure account go to [Azure Portal](http://portal.azure.com) or you can open a free one-month trial [Free Azure One-Month Trial](https://azure.microsoft.com/en-us/pricing/free-trial/). Inside of the Azure portal, simply select **New | Web + Mobile | Mobile App**, which is the starting point to configure your Azure Mobile App backend.

	![Create Azure Mobile App](Images/azure-create-mobile-app.png?raw=true "Create Azure Mobile App")

2. You’ll need to provide App Service name (this is the URL where your backend will live), configure your subscription, and set your resource group and plan. You can choose location where your app to be most active:
	
	![Configure Azure Mobile App](Images/azure-create-mobile-app-details.png?raw=true "Configure Azure Mobile App")
	
3. Once deployed, the Azure portal will bring you directly to the configuration screen with the settings tab open. All of the settings we’ll adjust can be found under the Mobile section:
	
	![Configure Azure Settings](Images/azure-settings.png?raw=true "Configure Azure Settings")
	
4. Our backend data will live in a database. Under the Data Connections section, select Add, and then configure a new SQL database:
	
	![Configure Database Settings](Images/azure-db.png?raw=true "Configure Azure Database")
	
5. When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database. Click OK on all open blades and Azure will begin to create the database for us on the fly. When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database. 
	
	![Azure Database Connection](Images/azure-db-connection.png?raw=true "Azure Database Connection")
 
6. Under Mobile settings is a new section called Easy Tables, which enable us to easily set up and control the data coming to and from the iOS and Android apps. Select the Easy Tables section, and we’ll be prompted with a big blue warning asking us to configure Easy Tables/Easy APIs:
	
	![Azure Easy Tables](Images/azure-easy-tables.png?raw=true "Azure Easy Tables")

7. Since we already setup the database, the only thing left to do is Initialize the app.
	
	![Azure Initialize the App](Images/azure-init-app.png?raw=true "Azure Initialize the App")

8. When the app will be fully initialized you can add our first table of the database named GameScore. If you are adding Azure Mobile Apps to an existing application, this table name should match the class name of the data you with to store. The beautiful part of Easy Tables is that it will automatically update and add the columns in the table dynamically based on the data we pass in. For this example, I’ll simply allow full anonymous access to the table, however it is possible to add authentication with Facebook, Twitter, Google, Microsoft, and other OAuth login providers.
	
	![Azure Add GameScore table](Images/azure-add-gamescore-table.png?raw=true "Azure Add GameScore table") 
