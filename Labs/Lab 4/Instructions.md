# Lab 4 - Azure Functions

The goal of this lab is to show how to create a Azure Function App using the Azure Portal and then deploy your own C# function(s) to this Function App.

## Part 1 - Create a Azure Function using Azure Portal

1. Log in to Azure Portal at portal.azure.com
2. Create a new resource group located in North Europe called `lab-faas-rg`
3. Navigate in to the newly created resource group and press the `Add` button.
4. Find a resource named "Function App". 
5. Press `Create`
   1. Choose the resource group `lab-faas-rg` if not already selected.
   2. Give the app a unique name of your choosing
   3. Select `.NET Core 3.1` as the runtime
   4. Select `North Europe` as region
   5. Rest of the settings can be left to default
   6. Press `Review + create`
   7. Press `Create`
6. Navigate to the newly created Azure Function resource and click the `Get publish profile` button on the top-menu.
7. Select the `App Keys` option in the left side menu under the `Functions` category
8. Copy the key named `default` and use it later where `<function-default-key>` is mentioned. (When calling the function)

## Part 2 - Deploy a Azure Function using Visual Studio

1. Open the Visual Studio solution named `hello-world-function` located inside this lab. 
2. Right click on the project in Visual Studio and choose `publish`
3. Press the button named `import profile` in the lower left corner.
4. Locate the `*.PublishSettings` file you downloaded earlier in this lab.
5. Press the button named `Publish` in the newly opened publish UI.
6. Navigate to `https://<your-unique-name>.azurewebsites.net/api/hello?name=Person&code=<function-default-key>` in a browser and confirm that the function has been deployed



## Links

- https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-first-azure-function
- https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-your-first-function-visual-studio
- https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview