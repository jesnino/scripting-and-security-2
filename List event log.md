# List event log
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/27/list-event-log/
```PowerShell
Get-WmiObject -Class Win32_NTEventLOgFile | Select-Object FileName, Sources

```
