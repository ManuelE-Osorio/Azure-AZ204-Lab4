# Azure-AZ204-Lab4
Lab 04: Construct a polyglot data solution

## Instructions

### 1. Setup Azure Cosmos DB

```bash
tenant=<tenant-id>
az login --tenant $tenant
resource-group-name=<resource-group-name>
az group create --location <location name> --name $resource-group-name
az group create --name $resourceGroupName --location westus2
az cosmosdb create --name $cosmosDBContainerName --resource-group $resourceGroupName --enable-free-tier true
az cosmosdb keys list --name $cosmosDBContainerName --resource-group $resourceGroupName
az cosmosdb keys list --name $cosmosDBContainerName --resource-group $resourceGroupName --type connection-strings
az cosmosdb show --name $cosmosDBContainerName --resource-group $resourceGroupName

```

### 2. Setup Azure Storage

To create the storage account the following commands where used.

```bash

storage-account-name=<storage-account-name>
az storage account create --name $storage-account-name  --resource-group <resource group name> --sku Standard_LRS
az storage account show-connection-string --name $storage-account-name -g <resource group name>
connection-string=<connection-string>
container-name=<container-name>
az storage container create --name $container-name --connection-string $connection-string --resource-group $resource-group-name
az storage account show-connection-string --name $storageAccountName -g $resourceGroupName
az storage blob upload-batch --destination $blobStorageName --source <directory-path>
az storage blob generate-sas --account-name $storageAccountName --permission r --blob-url <blob-url>
```

When the account is created, one can specify the following:

```
[--access-tier {Cold, Cool, Hot, Premium}]
[--kind {BlobStorage, BlockBlobStorage, FileStorage, Storage, StorageV2}]
[--public-network-access {Disabled, Enabled, SecuredByPerimeter}]
```
