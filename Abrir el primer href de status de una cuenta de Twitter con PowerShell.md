# Abrir el primer href de status de una cuenta de Twitter con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/08/13/abrir-el-primer-href-de-status-de-una-cuenta-de-twitter-con-powershell/
```PowerShell
$web=Invoke-WebRequest "https://twitter.com/microsoft"
Start-Process chrome ("https://twitter.com"+($web.Links | Where-Object {$_.href -match "status"} | Select-Object href)[0].href)

```
