# Leer datos de archivos .PSD1 en PowerShell 5
## PowerShell 
### URL: https://www.jesusninoc.com/2017/12/17/leer-datos-de-archivos-psd1-en-powershell-5/
```PowerShell
"@{
Nombre = ""Javier""
Apellidos = ""Monte""
}" | Out-File fichero.psd1

$datos = Import-PowerShellDataFile -Path .\fichero.psd1
$datos

```
