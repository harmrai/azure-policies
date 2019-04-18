# azure-policies

This repository contains some Azure policies which I have created and found useful at various client sites.

## Notes

### Get Aliases
Get aliases required for when defining types in a policy. Below is an example for retrieving the aliases for KeyVault using both PowerShell and AzureCLI

```powershell
Get-AzPolicyAlias -NamespaceMatch 'Microsoft.KeyVault' | Select-Object -ExpandProperty Aliases
```
```azurecli
az provider show --namespace Microsoft.KeyVault --expand "resourceTypes/aliases" --query "resourceTypes[].aliases[].name"
```

#### List Available Resources

```powershell
Get-AzPolicyAlias | Select-Object Namespace -Unique | Sort-Object Namespace
```

List of available resources which can be used with Azure Policy.
```
Namespace
---------
Microsoft.AnalysisServices
Microsoft.ApiManagement
Microsoft.Authorization
Microsoft.Automation
Microsoft.Batch
Microsoft.Blueprint
Microsoft.Cache
Microsoft.Cdn
Microsoft.Compute
Microsoft.ContainerRegistry
Microsoft.ContainerService
Microsoft.Databricks
Microsoft.DataFactory
Microsoft.DataLakeAnalytics
Microsoft.DataLakeStore
Microsoft.DBforMySQL
Microsoft.DBforPostgreSQL
Microsoft.Devices
Microsoft.DevTestLab
Microsoft.DocumentDB
Microsoft.EventGrid
Microsoft.EventHub
Microsoft.GuestConfiguration
Microsoft.HDInsight
microsoft.insights
Microsoft.KeyVault
Microsoft.Logic
Microsoft.MachineLearning
Microsoft.Network
Microsoft.NotificationHubs
Microsoft.OperationalInsights
Microsoft.RecoveryServices
Microsoft.Resources
Microsoft.Scheduler
Microsoft.Search
Microsoft.Security
Microsoft.ServiceFabric
Microsoft.Solutions
Microsoft.Sql
Microsoft.Storage
Microsoft.Web
```

### Create New Policy
```powershell
New-AzPolicyDefinition -Name 'auditKeyVaultSoftDelete' -Description 'Audit for Soft Delete Status on KeyVault' -Policy '.\softDelete-audit.json'
```
