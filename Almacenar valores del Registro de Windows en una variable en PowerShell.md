# Almacenar valores del Registro de Windows en una variable en PowerShell
## PowerShell, Registry 
### URL: https://www.jesusninoc.com/2017/07/29/almacenar-valores-del-registro-de-windows-en-una-variable-en-powershell/
```PowerShell
#Clave del registro sobre información de dispositivos USB conectados
$var=Get-Item -Path "Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR\*\*\"
$var

```
