# Ver los alias de los parámetros de un cmdlet
## PowerShell 
### URL: https://www.jesusninoc.com/2017/09/10/ver-los-alias-de-los-parametros-de-un-cmdlet/
```PowerShell
(Get-Command Get-Process).Parameters.Values | Select-Object Name,Aliases,Switchparameter

```
