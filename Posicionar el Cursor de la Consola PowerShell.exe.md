# Posicionar el Cursor de la Consola PowerShell.exe
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/07/posicionar-el-cursor-de-la-consola-powershell-exe/
```PowerShell
# Es necesario ejecutar el script en PowerShell.exe
# Listar procesos
Get-Process

# Posicionarse en la primera posición de la Consola
$esc = [char]27
$setCursorTop = "$esc[0;0H"
Write-Host "${setCursorTop} Volver a la posición 0,0"

# Listar procesos después e 5 segundos
Start-Sleep -Seconds 5
Get-Process

```
