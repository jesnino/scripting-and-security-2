# Crear y leer un código QR con un comando en Bash mediante WSL desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/01/crear-y-leer-un-codigo-qr-con-un-comando-en-bash-mediante-wsl-desde-powershell/
```PowerShell
powershell.exe Write-Host hola | wsl qrencode -o fich.png

.\fich.png

wsl zbarimg fich.png

```
