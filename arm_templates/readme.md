# Azure ARM Templates

### 1. Setup Azure CLI

Ensure you are logged in with Azure administrative credentials for your organization. 

Check the configure readme.md if you do not have Azure CLI installed on your computer.

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

<p>&nbsp;</p>

### 2. Create Azure Resource Group

### 3. Create Azure Key Vault

### 4. Set Secrets

```shell
az keyvault secret set --vault-name "<your-unique-keyvault-name>" --name "ExamplePassword" --value "hVFkk965BuUv"
```

### 5. Create Azure Storage

### 6. Create Azure Function App

