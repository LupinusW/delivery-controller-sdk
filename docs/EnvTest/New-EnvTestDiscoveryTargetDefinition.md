﻿# New-EnvTestDiscoveryTargetDefinition

   Creates a new EnvTestDiscoveryTargetDefinition object

## Syntax
```
New-EnvTestDiscoveryTargetDefinition -TestId <String> [-TargetIdType <String>] [-TargetId <String>] [-AdminAddress <String>] [<CommonParameters>]

New-EnvTestDiscoveryTargetDefinition -TestSuiteId <String> [-TargetIdType <String>] [-TargetId <String>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   Creates a new EnvTestDiscoveryTargetDefinition object that can be piped into Start-EnvTestTask to define one or more targets of execution, optionally including root objects for discovery.

## Related Commands
  * [Get-EnvTestDefinition](Get-EnvTestDefinition.html)
  * [Get-EnvTestSuiteDefinition](Get-EnvTestSuiteDefinition.html)
  * [Get-EnvTestTask](Get-EnvTestTask.html)
  * [Start-EnvTestTask](Start-EnvTestTask.html)
  * [Switch-EnvTestTask](Switch-EnvTestTask.html)
  * [Stop-EnvTestTask](Stop-EnvTestTask.html)
  * [Remove-EnvTestTask](Remove-EnvTestTask.html)
  * [Add-EnvTestTaskMetadata](Add-EnvTestTaskMetadata.html)
  * [Remove-EnvTestTaskMetadata](Remove-EnvTestTaskMetadata.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| TestId | Test identifiers. If specified, do not specify -TestSuiteId. | true | false | Empty |
| TestSuiteId | Test suite identifiers. If specified, do not specify -TestId. | true | false | Empty |
| TargetIdType | Describes the type of corresponding object passed with -TargetId | false | false | Empty |
| TargetId | The Ids that object tests or test suites will target. By default, other components are queried for objects related to these. | false | false | Empty |
| AdminAddress | Specifies the address of a XenDesktop controller the PowerShell snap-in will connect to. You can provide this as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value becomes the default. |

## Input Type
### 
   
## Return Values
### Citrix.EnvTest.Sdk.EnvTestDiscoveryTargetDefinition
   Defines a target of a task
## Examples

### EXAMPLE 1
```
$singleSimpleTestTaskTarget = New-EnvTestDiscoveryTargetDefinition -TestId Monitor_RegisteredWithConfigurationService
$singleSimpleTestTaskTarget | Start-EnvTestTask
```
   Description<br>-----------<br>Create a discovery target definition with a single test and no target object, then start a task based on it.
### EXAMPLE 2
```
$singleSimpleTestSuiteTaskTarget = New-EnvTestDiscoveryTargetDefinition -TestSuiteId Infrastructure
$singleSimpleTestSuiteTaskTarget | Start-EnvTestTask
```
   Description<br>-----------<br>Create a discovery target definition with a single test suite and no target object, then start a task based on it.
### EXAMPLE 3
```
$singleTestSuiteTaskTarget = New-EnvTestDiscoveryTargetDefinition -TestSuiteId Catalog -TargetIdType Catalog -TargetId $(Get-BrokerCatalog).Uuid
$singleTestSuiteTaskTarget | Start-EnvTestTask
```
   Description<br>-----------<br>Create a discovery target definition with a single test suite and a catalog target object, then start a task based on it.
### EXAMPLE 4
```
$singleSimpleTestSuiteTaskTarget = New-EnvTestDiscoveryTargetDefinition -TestSuiteId Infrastructure
$singleTestSuiteTaskTarget = New-EnvTestDiscoveryTargetDefinition -TestSuiteId Catalog -TargetIdType Catalog -TargetId $(Get-BrokerCatalog).Uuid
@($singleSimpleTestSuiteTaskTarget, $singleTestSuiteTaskTarget) | Start-EnvTestTask
```
   Description<br>-----------<br>Create two different discovery target definitions, put them in an array, then start a task based on both.
