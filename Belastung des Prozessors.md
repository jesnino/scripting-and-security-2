# Belastung des Prozessors
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/12/09/belastung-des-prozessors/
```PowerShell
Get-WmiObject win32_processor | Select-Object LoadPercentage

```
