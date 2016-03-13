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

<a name="Intended Audeience"></a>
### Intended Audience ###

This lab is intended for developer’s familiar with C# and Visual Studio. It does not require prior experience with Unity gaming platform.  

<a name="Setup" />
### Setup ###
In order to run the exercises in this module, you will need to set up your environment first.

1. Open Windows Explorer and browse to the module's **Source** folder.
1. Right-click on **Setup.cmd** and select **Run as administrator** to launch the setup process that will configure your environment and install the Visual Studio code snippets for this module.
1. If the User Account Control dialog box is shown, confirm the action to proceed.

> **Note:** Make sure you have checked all the dependencies for this module before running the setup.

<a name="CodeSnippets" />
### Using the Code Snippets ###

Throughout the module document, you will be instructed to insert code blocks. For your convenience, most of this code is provided as Visual Studio Code Snippets, which you can access from within Visual Studio 2015 to avoid having to add it manually. 

>**Note**: Each exercise is accompanied by a starting solution located in the **Begin** folder of the exercise that allows you to follow each exercise independently of the others. Please be aware that the code snippets that are added during an exercise are missing from these starting solutions and may not work until you have completed the exercise. Inside the source code for an exercise, you will also find an **End** folder containing a Visual Studio solution with the code that results from completing the steps in the corresponding exercise. You can use these solutions as guidance if you need additional help as you work through this module.

---

<a name="Exercises" />
## Exercises ##
This module includes the following exercises:

1. [Performing the first exercise](#Exercise1)
1. [Performing the second exercise](#Exercise2)

Estimated time to complete this module: **60 minutes**

>**Note:** When you first start Visual Studio, you must select one of the predefined settings collections. Each predefined collection is designed to match a particular development style and determines window layouts, editor behavior, IntelliSense code snippets, and dialog box options. The procedures in this module describe the actions necessary to accomplish a given task in Visual Studio when using the **General Development Settings** collection. If you choose a different settings collection for your development environment, there may be differences in the steps that you should take into account.

<a name="Exercise1" />
### Exercise 1: Performing the first exercise ###

In this exercise you will TBC.

<a name="Ex1Task1" />
#### Task 1 - TBC ####

In this task you will TBC.

1. Open **Visual Studio Community 2015** and select **File | New Project...** to start a new solution.

	![Creating a New Project](Images/creating-a-new-project.png?raw=true "Creating a New Project")

	_Creating a New Project_

	> **Note:** This is a placeholder step. For the Visual Studio screenshots use the Light theme (its the best to be printed).

1. The following shows a code snippet.

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
