# Ver los teléfonos móviles que se han conectado al sistema operativo
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/12/01/ver-los-telefonos-moviles-que-se-han-conectado-al-sistema-operativo/
```PowerShell
Get-PnpDevice | Where-Object { $_.class -EQ 'USBDevice' } | Select-Object FriendlyName

Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR\*\*\' | Where-Object { $_.FriendlyName } | Select-Object FriendlyName
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB\*\*\' | Where-Object { $_.FriendlyName } | Select-Object FriendlyName
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Enum\USB\*\*\' | Where-Object { $_.FriendlyName } | Select-Object FriendlyName
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Enum\USBSTOR\*\*\' | Where-Object { $_.FriendlyName } | Select-Object FriendlyName

```
