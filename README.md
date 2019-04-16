# azure-policies


## Notes

### Get Aliases
Get aliases required for when defining types in a policy. Below is an example for retrieving the aliases for KeyVault using both PowerShell and AzureCLI

```powershell
Get-AzPolicyAlias -NamespaceMatch 'Microsoft.KeyVault' | Select-Object -ExpandProperty Aliases
```
```AzureCLI
az provider show --namespace Microsoft.KeyVault --expand "resourceTypes/aliases" --query "resourceTypes[].aliases[].name"
```
