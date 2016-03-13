<a name="HOLTop" />
# Engaging Players with Azure #

---

<a name="Overview" />
## Overview ##

Enable your game with the Azure cloud technologies. Microsoft Azure offers hundreds of cross-platform services for any device: Android, iOS and Windows. In this lab, you will use a sample game and add Azure services to it. Your app will take advantage of multiple Azure services: you can choose what services to use in your game to expand it to its full potential.

<a name="Objectives" />
### Objectives ###
In this module, you will see how to:

- Connect your Unity game to Microsoft Azure
- Use Microsoft Azure App Service in your game 
- Store score, settings and game assets using Azure

<a name="Prerequisites"></a>
### Prerequisites ###

The following is required to complete this module:

- Windows 10.
- [Visual Studio Community 2015][1] or greater.
- [Unity 5.3.3][2]

[1]: https://www.visualstudio.com/products/visual-studio-community-vs
[2]: http://www.unity3d.com

> **Note:** You can take advantage of the [Visual Studio Dev Essentials]( https://www.visualstudio.com/en-us/products/visual-studio-dev-essentials-vs.aspx) subscription in order to get everything you need to build and deploy your app on any platform.

> **Note:** Intended Audience. This lab is intended for developer’s familiar with C# and Visual Studio. It does not require prior experience with Unity gaming platform. 

---

<a name="Exercises" />
## Exercises ##
This module includes the following exercises:

1. [Save game score and settings in Azure](#Exercise1)
2. [Performing the second exercise](#Exercise2)

Estimated time to complete this module: **60 minutes**

<a name="Exercise1" />
### Exercise 1: Save game score and settings in Azure ###

Most games need to save score and settings. Wouldn’t it be great if we can save user game score on one device, say a PC and then when the user comes back to another device: his/her tablet or phone, the score is there? In this lab you’ll be able to do it and learn how to use Microsoft Azure portal.

For the purpose of this lab we use a popular Unity Tanks! tutorial game available from Unity3D Web site. Tanks! is a very nice [multiplayer game example](http://unity3d.com/learn/tutorials/projects/tanks-tutorial). In this code lab you’ll learn how to modify this game to add Azure functionality to the game. At any moment you can access any step of this tutorial in code. Simply look at the project folder

- StepComplete folder contains complete code of the game
- Step3_AddedGameScore source of the game with game score added
 
![Tanks Game](Images/tanks-game.png?raw=true "Tanks Game")

<a name="Ex1Task1" />
#### Task 1 - Create Azure Mobile App ####

Microsoft Azure provides hundreds of features game developers can take advantage of. One of them is Mobile Apps. 

1. Go to [Azure Portal](http://windowsazure.com) and click Portal. If necessary, create a free account with Azure. Inside of the Azure portal, simply select **New | Web + Mobile | Mobile App**, which is the starting point to configure your Azure Mobile App backend.

	![Create Azure Mobile App](Images/azure-create-mobile-app.png?raw=true "Create Azure Mobile App")

2. You’ll need to provide App Service name (this is the URL where your backend will live), configure your subscription, and set your resource group and plan. You can choose location where your app to be most active:

	![Configure Azure Mobile App](Images/azure-create-mobile-app-details.png?raw=true "Configure Azure Mobile App")
	
3. Once deployed, the Azure portal will bring you directly to the configuration screen with the settings tab open. All of the settings we’ll adjust can be found under the Mobile section:

	![Configure Azure Settings](Images/azure-settings.png?raw=true "Configure Azure Settings")
	
4. Our backend data will live in a database. Under the Data Connections section, select Add, and then configure a new SQL database:

	![Configure Database Settings](Images/azure-db.png?raw=true "Configure Azure Database")
	
When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database.

	![Azure Database Connection](Images/azure-db-connection.png?raw=true "Azure Database Connection")
	
5. Click OK on all open blades and Azure will begin to create the database for us on the fly. When the data connection is created, it will appear in the Mobile Apps data connections blade, which means it’s time to set up the data that will go in the new database. Under Mobile settings is a new section called Easy Tables, which enable us to easily set up and control the data coming to and from the iOS and Android apps. Select the Easy Tables section, and we’ll be prompted with a big blue warning asking us to configure Easy Tables/Easy APIs:
 
	![Azure Easy Tables](Images/azure-easy-tables.png?raw=true "Azure Easy Tables")

Since we already setup the database, the only thing left to do is Initialize the app.

		
	(Code Snippet - _ModuleTitle - Ex1 - CodeSnippetSample_)
	<!-- mark:5-10 -->
	````C#
    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        // ...

        app.UseMvc(routes =>
        {
            routes.MapRoute(
                name: "default",
                template: "{controller=Home}/{action=Index}/{id?}");
        });
    }
	````

<a name="Ex1Task2" />
#### Task 2 - TBC ####

In this task you will TBC.

<a name="Exercise2" />
### Exercise 2: Performing the second exercise ###

In this exercise you will TBC.

<a name="Ex2Task1" />
#### Task 1 - TBC ####

In this task you will TBC.

---

<a name="Summary" />
## Summary ##

By completing this module you should have:

- Performed the first exercise
- Performed the second exercise

> **Note:** You can take advantage of the [Visual Studio Dev Essentials]( https://www.visualstudio.com/en-us/products/visual-studio-dev-essentials-vs.aspx) subscription in order to get everything you need to build and deploy your app on any platform.
