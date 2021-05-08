# Azure CLI Deployment Steps

## 1. Setup Azure CLI

Ensure you are logged in with Azure administrative credentials for your organization. You need to ensure [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) is installed on your computer.

```shell
az login
```
If you have multiple subscriptions, select the subscription you want to use. View your available subscriptions.

```shell
az account subscription list --query '[].{SubscriptionName:displayName, Id:subscriptionId}' --output table
```

Replace [SubscriptionId / SubscriptionName] with the SubscriptionId or SubscriptionName you want to use.

```shell
az account set --subscription [SubscriptionID/SubscriptionName]
```
Check you have selected the right Azure subscription.

```shell
 az account list --query '[].name' -o table
```
Once you have logged in and configured your environment. You will need to create an Azure Resource Group.

## 2. Create Azure Resource Group, Azure Storage, and Azure Key Vault

You will need to decide what Azure region to deploy your resources. You can view a complete list of available Azure regions your subscription has access to using the following:

```shell
az account list-locations --query "sort_by([].{DisplayName:displayName, Name:name}, &DisplayName)" --output table
```

You will need to use your selected region more than once. Replace the region with your selected region name and set it as an environmental variable:

```shell
echo -n "Enter deployment regions (i.e. centralus): "
read RG_LOCATION
```

Set the resource group name. Resource group names do _not_ need to be globally unique:

```shell
echo -n "Enter the name of your resource group, does not need to be globally unique: "
read RG_NAME
```

Create Azure resource group:

```shell
az group create --name $RG_NAME --location $RG_LOCATION
```

Setup a lock to prevent deletion of resources in resource group:

```shell
```

## 3. Create Azure Key Vault

## 4. Set Secrets

```shell
az keyvault secret set --vault-name "<your-unique-keyvault-name>" --name "ExamplePassword" --value "hVFkk965BuUv"
```

## 5. Create Azure Storage

## 6. Create Azure Function App

