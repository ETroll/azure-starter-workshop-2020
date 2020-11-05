# Lab 3 - Azure Key Vault and Configuration (Using a WebApp)

The goal of this lab is to show the usage of the Azure Key Vault, Azure App Configuration and how this can be beneficial for any Azure Application. Using Managed Identities the applications does not need to contain any credentials in configuration files. So the risk of a secret or a credential of some sorts getting leaked gets minimized.

## Part 1 - Create a Azure Key Vault

1. In Azure Portal to the resource group `lab-paas-rg` and press the `Add` button.
2. Find the resource named "Key Vault". (Use search or navigate in to the `Security` group and find it as before)
3. Press `Create`
   1. Choose the resource group `lab-paas-rg` if not already selected.
   2. Give the key vault a unique name of your choosing
   3. Select the North Europe region
   4. Press `Review + create` button
   5. Press `Create` button
4. Navigate to the newly created Key Vault and select the `Secrets` option in the left side menu under the `Settings` category
5. Click the `Generate/Import` button on the top-menu.
   1. Set `Name` to the value `MySecret`
   2. Set `Value` to the value `MySecretValue`
   3. Rest is set to default
   4. Press `Create`

## Part 2 - Create a Azure App Configuration Service

1. In Azure Portal to the resource group `lab-paas-rg` and press the `Add` button.
2. Find the resource named "App Configuration".
3. Press `Create`
   1. Choose the resource group `lab-paas-rg` if not already selected.
   2. Give the app configuration a unique name of your choosing
   3. Select the North Europe region
   4. Press `Review + create` button
   5. Press `Create` button
4. Navigate to the newly created App Configuration and select the `Configuration Explorer` option in the left side menu under the `Operations` category
5. Click the `Create` button on the top-menu and choose: `Key-value`
   1. Set `Key` value to `BackgroundColor`
   2. Set `Value` value to `#000000`
   3. Press `Apply`
6. Click the `Create` button on the top-menu and choose: `Key Vault reference`
   1. Set `Key` value to `HiddenSecret`
   2. Select the Key Vault we created earlier in the drop down
   3. Select the secret `MySecret` in the secret dropdown
   4. Press `Apply`

## Part 3 - Setting up a Managed User for the Web App

1. Navigate to the webapp we created in lab 2 (The app with the Razor Pages app)
2. Select the `Identity` option in the left side menu under the `Settings` category
3. Make sure that the `System assigned` tab is selected
4. Flip the status toggle to `on` and press `Save` above
5. Copy the `Object ID` guid and store it somewhere temporarily. (You might need it, but often not)
6. Navigate to the App Configuration service created in Part 2
7. Select the `Access control` option in the left side menu
8. Press `Add` on the top menu and choose `Add role assignment`
   1. In the `Role` dropdown choose `App Configuration Data Reader`
   2. In the `Assign Access to` dropdown choose `App Service`
   3. Select the App Service that you created in the results list below
   4. Press `Save`
9. Navigate to the Key Vault service created in Part 1
10. Select the `Access control` option in the left side menu
11. Press `Add` on the top menu and choose `Add role assignment`
    1. In the `Role` dropdown choose `Reader`
    2. In the `Assign Access to` dropdown choose `App Service`
    3. Select the App Service that you created in the results list below
    4. Press `Save`
12. Select the `Access policies` option in the left side menu under the `Settings` category
13. Press 'Add Access Policy' Button/link
14. In the `Configure from template` dropdown choose: `Secret Management`
15. In the `Select principal` window paste the guid you copied before into the search field and select the web app.
16. Press `Select` button at the bottom
17. Press `Add button` when the select principal window has closed.
18. Press the `Save button` on the top menu after you returned from the add access policy window
19. Select the `Overview` option in the left side menu 
20. Copy the URL of the App Configuration instance (next to the `Endpoint` label) and save it for later

## Part 4 - Update the Web App to use App Configuration for both Configuration values and Secrets

1. Open up the `webapp-razorpage` solution in `Lab 3`.
2. Open the `appsettings.json` file and replace `AppConfig:Endpoint` variable with the url you copied from App configuration earlier.
3. Import the publish profile as you did on Lab 2
4. Publish
5. Open the URL for the web app and the website should display your secret and have a black top menu.


## Links
- https://docs.microsoft.com/en-us/azure/key-vault/general/quick-create-portal
- https://docs.microsoft.com/en-us/azure/key-vault/general/tutorial-net-create-vault-azure-web-app
- https://docs.microsoft.com/en-us/azure/azure-app-configuration/overview
- https://docs.microsoft.com/en-us/azure/azure-app-configuration/quickstart-dotnet-core-app
- https://docs.microsoft.com/en-us/azure/active-directory/managed-identities-azure-resources/overview
- https://docs.microsoft.com/en-us/dotnet/api/overview/azure/identity-readme?view=azure-dotnet
- https://docs.microsoft.com/en-us/azure/azure-app-configuration/howto-integrate-azure-managed-service-identity
- https://docs.microsoft.com/en-us/azure/key-vault/general/assign-access-policy-portal