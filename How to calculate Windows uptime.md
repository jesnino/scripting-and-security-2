# How to calculate Windows uptime
## PowerShell 
### URL: https://www.jesusninoc.com/2017/07/26/how-to-calculate-windows-uptime/
```PowerShell
String]$Start=net statistics server | Select-String "sticas desde"
$StartDate=[datetime]$Start.split(" ")[3]

$EndDate=Get-Date -Format 'HH:mm:ss'

New-TimeSpan –Start $StartDate –End $EndDate

```
