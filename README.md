<h4>Azure Resource Manager Template Sample</h4>

Template files allow us to configure and automate deployments with JSON format.For easy use and intellisense of ARM template properties, you should add [Azure Resource Manager (ARM) Tools](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) extension to your VSCode.

<h5>Azure CLI deployment steps</h5>

```
az login // login to azure account
az account set --subscription "{subscription-name}" // set the default subscription
az configure --defaults group={resource-group-name} // set the default resource group

//define variables
templateFile="azuredeploy.json"
today=$(date +"%d-%b-%Y")
deploymentName="blanktemplate-"$today

//deploy template to azure
az deployment group create \
  --name $DeploymentName \
  --template-file $templateFile \
  --parameters storageName={your-unique-name} storageSKU={choose-from-allowed-options} 
```