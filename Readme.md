# Azure Introduction Workshop 2020

This Azure introduction workshop is ment as a kickstart to Microsoft Azure for developers. It has a estimated runtime of 6-7 hours and covers a small subset of the services available on Azure. 

## Tools needed by the attendees:
 - Azure Subscription
 - A browser (Chromium based is preferred for Azure Portal)
 - Git
 - Azure CLI
 - .NET Core SDK
 - Visual Studio / Visual Studio Code. (Visual Studio preferred)
 - (opt) Azure Storage Explorer

## Part 1 - Using the administration tools (1h)

### Topics:
 - Azure Portal
 - Azure CLI
 - Azure Basics
    - Resource Groups
    - Azure resource types
    - Virtual Machines
    - Virtual Networks
    - NSG
    - Disks
    - Storage

### Lecture 1 - The cloud and Azure in 15 min (15 min)

Notes to self regarding this lecture: Try to explain that "The cloud" is really just a "self-service" data center with many pre-made solutions (platforms) built on top of the rentable hardware. Mention and explain IaaS along side this.

### Lab 1 (30 mins)
Log in to Azure using the portal and create a resource group in North Europe. In this resource group you should create a virtual machine with windows and a public IP.

Log in to Azure using the Azure CLI. Create a resource group in West Europe. Create a Azure Storage Account in this resource group. Upload a file to the blob storage using the Azure Portal or Azure Storage Explorer

### Lab1 Solution and questions (15 min)

(See instructions)

## Part 2 - PaaS with Azure Web Apps (1h)

### Lecture 2 - About PaaS and Web Apps (15 min)
 - What is PaaS?
 - What separates it from IaaS
 - Azure Web Apps is a PaaS
 - What can Azure Web Apps do?
    - IIS
    - .NET Core
    - Containers
    - Many other runtimes and languages
 - Pricing models and difference in regards to scaling

### Lab 2 (30 min)

Delete the resource groups from the previous lab if you have not done so already.
Create a new resource group in North Europe. Create and deploy a WebApp with the basic pricing model.

Deploy a container (to be decided) to the Web app and have a look at the deployed site.
Deploy a .NET Core Razor Pages app that is supplied. (Build and deploy via Visual Studio)

### Lab 2 Solution and questions (15 min)

TODO

## Part 3 - Azure Key Vault and Configuration

### Lecture 3 - Key Vault and Config (10 min)
 - AKV intro
 - Azure Configuration intro
 - Benefits of using a key store and configuration store
 - Integrated into most Azure services
 - Managed users in Azure - Why use! Apps needs access too ;)

### Lab 3 Use Keyvault, Config and Managed users (20 min)

Using the same Web app as previous lab. (Or create new) add a managed user to that web app. Create a new Azure Key Vault and Azure Configuration. Give access to the managed user you created earlier. Create a secret in Azure Key Vault. Add the URL to the key vault in the Azure Configuration. Use a pre-made Web App for this lab and replace the URI to the Azure configuration service and add a config key with the name of the secret you created. Deploy the application and see your secret spelled on the webpage.

### Lab 3 Solution and questions (10 min)

TODO

## Part 4 - Azure Functions 

## Part 5 - Azure Logic Apps and Azure Event Grid

<!-- ## Part 6 - Azure Event Grid / Service Bus with Functions -->



Main topics
 - Functions
 - Web Apps
 - Azure Service Bus (Kanskje kombinert med Azure Functions?)
 - Azure Event Grid ? - Kombinert med Azure Functions
 - Azure Logic Apps
 - Azure SQL Server
 - Static web sites on Azure Storage? (Can be some lecture stuff and not lab? Same as on NDC?)
 - Azure Container Instances
 - Azure Key Vault
 - Azure Configuration
