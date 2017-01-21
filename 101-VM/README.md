# Read Me for For Azure VM Creation (UbuntuOS)
## Pre-requsites
    You need to have account in Azure for you to be able to use this.
## Commands to run and its purpose
#### azure login
    This will be done one in a session when you try to login to Azure
#### azure account list
    Once you have logged in - make sure you have access to the subscription you want to work on. 
    If you have multiple subscription make sure you are in the correct subscription.     
#### azure group create -n "ExampleRS-bnr" -l "WestUS"
    The above command creates a new Resource Group in Azure within the specified subscription and 
    location of the ResourceGroup is also specified.
#### azure group deployment create -f azuredeploy.json -g ExampleRS-bnr -n ExampleRS-bnrvm01
    The above command creates the storage account within the mentioned resource group. 
    When you run the command you will be prompted for a resource group name. Please provide the name all in lowercase, just alphanumeric.

### Input Parameter 
    When the deployment runs it will prompt the user for various inputs.
    Note: If the resource is already present - it will not be recreated.

##### _newStorageAccountName_ 
    Unique DNS name for the storage account where the virtual machine's disks will be placed. 
##### _adminUsername_
    User name for the virtual machine
##### _adminPassword_
    Password for the virtual machine
##### _vmName_
    Unique VM name which will be the host name virtual machine. This name will be used for all the resources attached to this VM.
    For example DNS name will become <vmname>.<location>.cloudapp.azure.net
##### _vmSize_
    These are VMSize allowed  - for this templated - only 3 values are allowed - they are: Standard_D1, Standard_D2, Standard_D3
##### _location_
    Region on which this VM will be created. ALlowed values on this templates are  WestUS, EastUS
##### _ubuntuOSVersion_
    Version of UbuntuOS needed, with some restriction.AllowedValues are  12.04.5-LTS, 14.04.2-LTS,15.04. 
    However the defaultValue": 14.04.2-LTS. Since a default value is provided - you will not be prompted to enter a value.
### Sample Input Values:
    newStorageAccountName:  storageAzsWest
    adminUsername:  deployer
    adminPassword:  <masked>
    vmName:  devApp01
    vmSize:  Standard_D1
    location:  WestUS   

Once the deployment is successful - look for the status and ensure that you are able to SSH to box using 
the username password you provided.