# Crear una entrada del Registro desde PowerShell que permita ejecutar siempre un programa al iniciar la sesión de un usuario
## PowerShell, Registry 
### URL: https://www.jesusninoc.com/2017/10/03/crear-una-entrada-del-registro-desde-powershell-que-permita-ejecutar-siempre-un-programa-al-iniciar-la-sesion-de-un-usuario/
```PowerShell
Set-Location Registry::HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\run

Get-Item -Path Registry::HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\run

#Arrancar PowerShell al iniciar sesión del usuario
New-ItemProperty -Path . -Name powershell -PropertyType String -Value "powershell.exe"

Get-Item -Path Registry::HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\run

```
