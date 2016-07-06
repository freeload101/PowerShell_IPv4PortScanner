# PowerShell - IPv4 Port Scanner

Powerful asynchronus IPv4 Port Scanner for PowerShell.

## Description

This powerful asynchronus IPv4 Port Scanner allows you to scan every Port-Range you want (500 to 2600 would work). Only TCP-Ports are scanned.

The result will contain the Port number, Protocol, Service name, Description and the Status.

![Screenshot](Documentation/Images/New-IPv4PortScan.png?raw=true "New-IPv4PortScan")

To reach the best possible performance, this script uses a [RunspacePool](https://msdn.microsoft.com/en-US/library/system.management.automation.runspaces.runspacepool(v=vs.85).aspx). As you can see in the following screenshot, the individual tasks are distributed across all cpu cores:

![Screenshot](Documentation/Images/New-IPv4PortScan_CPUusage.png?raw=true "CPU usage")

If you are looking for a module... you can find it [here](https://github.com/BornToBeRoot/PowerShell)!

## Syntax

```powershell
.\New-IPv4PortScan.ps1 [-ComputerName] <String> [[-StartPort] <Int32>] [[-EndPort] <Int32>] [[-Threads] <Int32>] [[-Force]] [[-UpdateList]] [<CommonParameters>]
```

## Example

```powershell
PS> .\New-IPv4PortScan.ps1 -ComputerName fritz.box -EndPort 500

Port Protocol ServiceName  ServiceDescription               Status
---- -------- -----------  ------------------               ------
  21 tcp      ftp          File Transfer Protocol [Control] open
  53 tcp      domain       Domain Name Server               open
  80 tcp      http         World Wide Web HTTP              open
 139 tcp      netbios-ssn  NETBIOS Session Service          open
 445 tcp      microsoft-ds Microsoft-DS                     open
``` 