# Buscar actualizaciones instaladas con PowerShell
## PowerShell, Updates 
### URL: https://www.jesusninoc.com/2017/09/12/buscar-actualizaciones-instaladas-con-powershell/
```PowerShell
$Sesion = New-Object -ComObject Microsoft.Update.Session
$actualizacion = $Sesion.CreateUpdateSearcher().Search("IsInstalled=1").Updates
$actualizacion | Select-Object Title

```
