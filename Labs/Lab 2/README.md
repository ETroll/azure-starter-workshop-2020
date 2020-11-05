# Lab 2 - PaaS and Web Apps

The goal of this lab is to show one of the pillars of the PaaS services on Microsoft Azure and use the Azure Portal and Visual Studio to deploy applications to a PaaS service.

## Part 1 - Azure Web App using Visual Studio

1. Log in to Azure Portal at portal.azure.com
2. Delete the resource group you created in previous lab if you have not done so.
3. Create a new resource group located in North Europe called `lab-paas-rg`
4. Navigate in to the newly created resource group and press the `Add` button.
5. Find a resource named "Web App". (Use search or navigate in to the `Web` group and find it)
6. Press `Create`
   1. Choose the resource group `lab-paas-rg` if not already selected.
   2. Give the app a unique name of your choosing
   3. Select the `.NET Core 3.1 (LTS)` runtime
   4. Select the North Europe region
   5. Select `Linux` as operating system
   6. Select the `B1` SKU
   7. Rest of the settings not mentioned here can be set at default values
   8. Press `Review + create` button
   9. Press `Create` button
   10. Wait for the Web App to be created. (Tip: Check the `Bell` icon in upper right corner to see progress of all running tasks)
7. Navigate to the newly created Web App resource and click the `Get publish profile` button on the top-menu.
8. Note the Web App URL listed on the top section of the Web App pane after the `URL` label. (Will be `https://<your-name>.azurewebsites.net`)
9. Open the Visual Studio solution named `webapp-razorpage` located inside this lab. 
10. Right click on the project in Visual Studio and choose `publish`
11. Press the button named `import profile` in the lower left corner.
12. Locate the `*.PublishSettings` file you downloaded earlier.
13. Press the button named `Publish` in the newly opened publish UI.
14. Navigate to `https://<your-name>.azurewebsites.net/` in a browser and confirm that the website is running.


## Part 2 - Azure Web Apps using Docker Containers

1. In Azure Portal to the resource group `lab-paas-rg` and press the `Add` button.
2. Find the resource named "Web App". (Use search or navigate in to the `Web` group and find it as before)
3. Press `Create`
    1. Choose the resource group `lab-paas-rg` if not already selected.
    2. Give the app a unique name of your choosing
    3. Select `Docker` as the `Publish` option
    4. Select the North Europe region
    5. Select the `App Service Plan` used in the previous part
4.  Navigate to the newly created Web App resource
5.  Select the `Container settings` option in the left side menu under the `Settings` category
6.  Under the `Full Image Name and Tag` input box in the pane that appeared input the following: `mcr.microsoft.com/dotnet/core/samples:aspnetapp`
7.  Press `Save`
8.  You can follow the image download and startup by pressing the `Refresh` button under the `Logs` section.
9.  After the image has been downloaded and started you can now naviagate to `https://<your-name-docker>.azurewebsites.net/` to see the newly deployed website.



## Links
- https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal
- https://docs.microsoft.com/en-in/azure/app-service/overview
- https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start?view=aspnetcore-3.1&tabs=visual-studio
- https://docs.microsoft.com/en-us/visualstudio/deployment/tutorial-import-publish-settings-azure?view=vs-2019