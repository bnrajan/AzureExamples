# Read Me for For Azure Storage Account create
## Pre-requsites
    You need to have account in Azure for you to be able to use this.
## Commands to run and its purpose
#### azure login
    This will be done one in a session when you try to login to Azure
#### azure account list
    Once you have logged in - make sure you have access to the subscription you want to work on. If you have multiple subscription make sure you are in the correct subscription.     
#### azure group create -n "ExampleRS-bnr" -l "WestUS"
The above command creates a new Resource Group in Azure within the specified subscription and location of the ResourceGroup is also specified.
#### azure group deployment create -f azuredeploy.json -g ExampleRS-bnr -n ExampleRS-bnr-storage-account01
The above command creates the storage account within the mentioned resource group. When you run the command you will be prompted for a resource group name. Please provide the name all in lowercase, just alphanumeric.
    