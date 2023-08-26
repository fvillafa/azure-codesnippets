# azure-codesnippets

Repo to put either PowerShell or az cli snippets that I use daily.

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
