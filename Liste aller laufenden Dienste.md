# Liste aller laufenden Dienste
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2017/02/20/liste-aller-laufenden-dienste/
```PowerShell
Get-WmiObject -query "select * from Win32_Service"

```
