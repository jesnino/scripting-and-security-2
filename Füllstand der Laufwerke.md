# Füllstand der Laufwerke
## PowerShell 
### URL: https://www.jesusninoc.com/2017/04/07/fuellstand-der-laufwerke/
```PowerShell
Get-Wmiobject Win32_logicaldisk | Select-Object deviceid,size,freespace

```
