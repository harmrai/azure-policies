# azure-policies


###### Get aliases required for when defining types in a policy. Below is an example of both PowerShell and AzureCLI

```powershell
Get-AzPolicyAlias -NamespaceMatch 'Microsoft.KeyVault' | Select-Object -ExpandProperty Aliases
```
