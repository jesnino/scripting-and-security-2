# Verificar si un comando de Windows se ha ejecutado correctamente desde PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/05/12/verificar-si-un-comando-de-windows-se-ha-ejecutado-correctamente-desde-powershell/
```PowerShell
ping.exe www.jesusninoc.com -n 2 -w 2000
if($LASTEXITCODE -eq 0){"Ping se ha ejecutado correctamente"}

ping.exe www.jesusninoc.co -n 2 -w 2000
if($LASTEXITCODE -eq 1){"Ping no se ha ejecutado correctamente"}

```
