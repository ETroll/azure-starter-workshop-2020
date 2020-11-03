# Lab 1 - IaaS and Administration Tools

The goal of this lab is to try out two of the main administration tools used to interact with Microsoft Azure and create some IaaS services.

## Part 1 - Azure Portal and VM

1. Log in to the Azure portal at portal.azure.com
2. Create a new resource group located in North Europe and give it the name `lab-iaas-rg`.
3. Navigate in to the newly created resource group and press the `Add` button.
4. Find a resource named "Windows Server 2016 Datacenter". (Use search or navigate in to the `Compute` group and find it)
   1. Give it a name of your choice
   2. Leave most settings to default except:
      1. Size - Choose DS1_v2
      2. Set a username and password
   3. Press `Review and create` (You can navigate trough all the settings to see what gets created if you like before you press this button. But all defaults are OK)
   4. Press `Create`
   5. Wait for the VM to be created. (Tip: Check the `Bell` icon in upper right corner to see progress of all running tasks)
   6. Go to the newly create Virtual Machine and connect to the `Public IP address` specified using RDP.
   7. You now have a VM running on Azure that you can connect to publicly.

## Part 2 - Azure CLI and Azure Storage

1. We will use the previously created resoruce group `lab-iaas-rg`. So no need to create another one
2. Log in to Azure in the CLI using the command `az login`
3. List all Azure subscriptions using the command: `az account list --output table`
4. Make the MSDN Subcription the active one (if not already) by using the command: `az account set --subscription <subcription-name-or-guid>`
5. Run the command `az account list --output table` again and verify that the MSDN subscription has `IsActive` flag set.
6. Create a Azure Storage Account using the command: `az storage account create --name <your-name> --resource-group lab-iaas-rg --location northeurope --sku Standard_LRS`
7. List the private keys used to authenticate with the Storage account using the command: `az storage account keys list --account-name <your-name> --resource-group lab-iaas-rg --output table`
8. Create a new `Storage Container (Blob)` on the newly created Storage Account using the secret key: `az storage container create -n datablob1 --account-name <your-name> --account-key <your-key>`
9. Use either the Azure Portal or the Azure Storage Explorer to naviagte to your newly created storage account and blob.
   1.  Portal:
       1.  Go to the resouce group you created earlier `lab-iaas-rg`.
       2.  Select the Storage account resource named `<your-name>`
       3.  Select `Storage Explorer (Preview)` on the left side menu that appears.
       4.  Expand the `BLOB CONTAINERS` node and select `datablob1`
       5.  Use the UI that appears right of the menu to use the `Upload` button to upload a file
   2.  Azure Storage Explorer:
       1.  Start the Azure Storage Explorer application
       2.  Log in to your account
       3.  On the Tree View on the left side navigate to the `Storage Accounts` listings for your subscription and expand `<your-name>` and `Blob Containers` and select `datablob1`
       4.  Upload a file by dragging and dropping or using the `Upload button`


## Links

 - https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal
 - https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal
 - https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-cli
 - https://docs.microsoft.com/en-us/cli/azure/manage-azure-subscriptions-azure-cli
 - https://docs.microsoft.com/en-us/cli/azure/reference-index?view=azure-cli-latest

