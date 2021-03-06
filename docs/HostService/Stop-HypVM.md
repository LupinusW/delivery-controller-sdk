﻿# Stop-HypVM

   Stops a VM by issuing a Shutdown request

## Syntax
```
Stop-HypVM [-LiteralPath] <String> [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   Use this command to change the power state of a VM from running to stopped.

## Related Commands
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| LiteralPath | Specifies the path within a hosting unit provider to the virtual machine item to stop. The path specified must be in one of the following formats: <drive>:\Connections\<Connection Name>\<Item Path of VM object> or  <drive>:\Connections\{<connection Uid>\<Item Path of VM object>} or <drive>:\HostingUnits\<HostingUnit Name>\<Item Path of VM object> or  <drive>:\HostingUnits\{<hostingUnit Uid>\<Item Path of VM object>} | true | true (ByValue) |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snap-in will connect to.  This can be provided as a host name or an IP address. | false | false | LocalHost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### System.string<br>          You can pipe a string that contains a path.
   
## Return Values
### System.void.
   ## Notes
   In the case of failure, the following errors can result.<br>    Error Codes<br>    -----------<br>    InputHypervisorItemPathInvalid<br>    The path provided is not to an item in a sub-directory of a connection item or a hosting unit item.<br>    InvalidHypervisorItemPath<br>    No item exists with the specified path.<br>    InvalidHypervisorItem<br>    The item specified by the path exists, but is not a VM Item.<br>    HypervisorInMaintenanceMode<br>    The hypervisor is in maintenance mode.<br>    DatabaseError<br>    An error occurred in the service while attempting a database operation.<br>    DatabaseNotConfigured<br>    The operation could not be completed because the database for the service is not configured.<br>    CommunicationError<br>    An error occurred while communicating with the service.<br>    PermissionDenied<br>    The user does not have administrative rights to perform this operation.<br>    ExceptionThrown<br>    An unexpected error occurred.  For more details, see the Windows event logs on the controller being used or examine the XenDesktop logs.
## Examples

### EXAMPLE 1
```
C:\PS>Stop-HypVM -LiteralPath XDHyp:\Connections\MyConnection\MyVm.vm
```
   Description<br>-----------<br>This command stops a VM called 'MyVm.vm' within a hypervisor connection called 'MyConnection'.
