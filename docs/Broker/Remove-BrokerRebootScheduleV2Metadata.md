﻿# Remove-BrokerRebootScheduleV2Metadata

   Deletes RebootScheduleV2 Metadata from the RebootScheduleV2 objects

## Syntax
```
Remove-BrokerRebootScheduleV2Metadata [-InputObject] <RebootScheduleV2[]> -Name <String> [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Remove-BrokerRebootScheduleV2Metadata cmdlet deletes Metadata from the RebootScheduleV2 objects.

## Related Commands
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | Specifies the RebootScheduleV2 object's instance whose Metadata is to be deleted. | true | true (ByValue) |  |
| Name | Specifies the name of the Metadata to be deleted | true | false |  |
| LoggingId | Specifies the identifier of the high level operation that this cmdlet call forms a part of. Desktop Studio and Desktop Director typically create High Level Operations. PowerShell scripts can also wrap a series of cmdlet calls in a High Level Operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### Citrix.Broker.Admin.SDK.BrokerRebootScheduleV2
   You can pipe the RebootScheduleV2 to delete the metadata.
## Return Values
### None
   
## Examples

### EXAMPLE 1
```
C:\PS> Remove-BrokerRebootScheduleV2Metadata -InputObject $obj-Uid -Name "MyMetadataName"
```
   Description<br>-----------<br>This command deletes the Metadata "MyMetadataName" key-value pair for the RebootScheduleV2 whose instance is pointed by $obj-Uid
### EXAMPLE 2
```
C:\PS> Get-BrokerRebootScheduleV2 | Remove-BrokerRebootScheduleV2Metadata -Name "MyMetadataName"
```
   Description<br>-----------<br>This command deletes the Metadata "MyMetadataName" key-value pair for all the RebootScheduleV2 in the site
