# Codificar un fichero BMP en Base64 con PowerShell
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/05/05/codificar-un-fichero-bmp-en-base64-con-powershell/
```PowerShell
#Leer el contenido de un fichero en ASCII
Write-Host "Contenido del fichero BMP blanco en ASCII"
gc .\blanco.bmp

#Codificar un fichero BMP en Base64
$path=".\blanco.bmp"
[System.Convert]::ToBase64String((Get-Content $path -Encoding Byte))

#Abrir el resultado en Google Chrome
Start-Process chrome "data:image/jpg;base64,Qk06AAAAAAAAADYAAAAoAAAAAQAAAAEAAAABABgAAAAAAAQAAAAAAAAAAAAAAAAAAAAAAAAA////AA=="

```
