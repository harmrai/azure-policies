# azure-policies


## Notes

### Get Aliases
Get aliases required for when defining types in a policy. Below is an example for retrieving the aliases for KeyVault using both PowerShell and AzureCLI

```powershell
Get-AzPolicyAlias -NamespaceMatch 'Microsoft.KeyVault' | Select-Object -ExpandProperty Aliases
```
```azurecli
az provider show --namespace Microsoft.KeyVault --expand "resourceTypes/aliases" --query "resourceTypes[].aliases[].name"
```

### Create New Policy
```powershell
$definition = New-AzPolicyDefinition -Name 'auditKeyVaultSoftDelete' -Description 'Audit for Soft Delete Status on KeyVault' -Policy '.\softDelete-audit.json'
```
