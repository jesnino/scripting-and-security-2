# Mostrar información sobre las reglas del Firewall de Windows con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/09/mostrar-informacion-sobre-las-reglas-del-firewall-de-windows-con-powershell/
```PowerShell
$f = New-object -comObject HNetCfg.FwPolicy2
$f.Rules | Select-Object name,applicationname,localports,remoteports | Out-GridView

```
