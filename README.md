# azure-codesnippets

Repo to put either PowerShell or az cli snippets that I use daily.

## List & set the subscription to work on

### PowerShell

```
Set-AzContext -SubscriptionId <subscription_id>
```
### az cli

To list available ones: 
```
az account list --output table
```
To set:
```
az account set -s <subscription_id>
```
or
```
az account set --subscription <subscription_id>
```
Also by name:
```
az account -n <subscription_name>
```
or
```
az account set --name <subscription_name>
```
## Verify encryption status

### PowerShell
``` 
Get-AzVmDiskEncryptionStatus -ResourceGroupName <resourcegroup> -VMName <vmname>
```
### az cli
```
az vm encryption show -g <resourcegroup> -n <vmname> --query "disks[*].[name, statuses[*].displayStatus]"  -o table
```
### Source fore more options:

https://learn.microsoft.com/en-us/azure/virtual-machines/linux/how-to-verify-encryption-status
