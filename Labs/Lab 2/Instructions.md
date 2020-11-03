# Lab 2 - PaaS and Web Apps

The goal of this lab is

## Part 1 - Azure Web App using Visual Studio

1. Log in to Azure Portal at portal.azure.com
2. Delete the resource group you created in previous lab if you have not done so.
3. Create a new resource group located in North Europe called `lab-paas-rg`
4. Navigate in to the newly created resource group and press the `Add` button.
5. Find a resource named "Web App". (Use search or navigate in to the `Web` group and find it)
   1. Choose the resource group `lab-paas-rg` if not already selected.
   2. Give the app a unique name of your choosing
   3. Select the `.NET Core 3.1 (LTS)` runtime
   4. Select the North Europe region
   5. Select the `B1` SKU
   6. Rest of the settings not mentioned here can be set at default values
   7. Press `Review + create` button
   8. Press `Create` button
   9. Wait for the Web App to be created. (Tip: Check the `Bell` icon in upper right corner to see progress of all running tasks)
6. Navigate to the newly created Web App resource and click the `Get public profile` button on the top-menu.
7. Note the Web App URL listed on the top section of the Web App pane after the `URL` label. (Will be `https://<your-name>.azurewebsites.net`)
8. Clone the git repository located at: 


## Links
- https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal
- https://docs.microsoft.com/en-in/azure/app-service/overview
- 



Delete the resource groups from the previous lab if you have not done so already.
Create a new resource group in North Europe. Create and deploy a WebApp with the basic pricing model.

Deploy a container (to be decided) to the Web app and have a look at the deployed site.
Deploy a .NET Core Razor Pages app that is supplied. (Build and deploy via Visual Studio)