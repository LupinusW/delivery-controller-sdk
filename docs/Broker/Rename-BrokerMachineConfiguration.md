﻿# Rename-BrokerMachineConfiguration

   Renames a machine configuration.

## Syntax
```
Rename-BrokerMachineConfiguration [-InputObject] <MachineConfiguration[]> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Rename-BrokerMachineConfiguration [-Name] <String> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Rename-MachineConfiguration cmdlet changes the name of a machine configuration. A machine configuration cannot have the same name as another machine configuration associated with the same slot.

## Related Commands
  * [New-BrokerMachineConfiguration](New-BrokerMachineConfiguration.html)
  * [Get-BrokerMachineConfiguration](Get-BrokerMachineConfiguration.html)
  * [Set-BrokerMachineConfiguration](Set-BrokerMachineConfiguration.html)
  * [Remove-BrokerMachineConfiguration](Remove-BrokerMachineConfiguration.html)
  * [Add-BrokerMachineConfiguration](Add-BrokerMachineConfiguration.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | Machine configuration to rename. | true | true (ByValue) | None |
| Name | Current name of machine configuration. | true | true (ByPropertyName) | None |
| NewName | New name for machine configuration. This may have the form "ConfigurationSlotName\MachineConfigurationName" or "MachineConfigurationName". If the "ConfigurationSlotName" is provided it must match the name of the configuration slot that the machine configuration is associated with. | true | false | None |
| PassThru | This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it returns the affected record. | false | false | False |
| LoggingId | Specifies the identifier of the high level operation that this cmdlet call forms a part of. Desktop Studio and Desktop Director typically create High Level Operations. PowerShell scripts can also wrap a series of cmdlet calls in a High Level Operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### Citrix.Broker.Admin.SDK.MachineConfiguration
   Machine configuration to rename.
## Return Values
### None or Citrix.Broker.Admin.SDK.MachineConfiguration
   This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it generates a Citrix.Broker.Admin.SDK.MachineConfiguration object.## Notes
   The configuration slot can not be changed. Thus the left term of the Name and NewName must match.
## Examples

### EXAMPLE 1
```
Rename-BrokerMachineConfiguration -Name "UPM\All Departments" -NewName "UPM\Finance Department"
```
   Description<br>-----------<br>Renames the machine configuration named "UPM\All Departments" to "UPM\Finance Department".
### EXAMPLE 2
```
Rename-BrokerMachineConfiguration -Name "UPM\All Departments" -NewName "Finance Department"
```
   Description<br>-----------<br>Renames the machine configuration named "UPM\All Departments" to "UPM\Finance Department".
