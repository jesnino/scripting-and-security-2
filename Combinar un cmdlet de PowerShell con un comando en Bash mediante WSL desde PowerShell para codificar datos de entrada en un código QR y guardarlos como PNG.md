# Combinar un cmdlet de PowerShell con un comando en Bash mediante WSL desde PowerShell para codificar datos de entrada en un código QR y guardarlos como PNG
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/30/combinar-un-cmdlet-de-powershell-con-un-comando-en-bash-mediante-wsl-desde-powershell-para-codificar-datos-de-entrada-en-un-codigo-qr-y-guardarlos-como-png/
```PowerShell
powershell.exe Write-Host hola | wsl qrencode -o fich.png
.\fich.png

```
