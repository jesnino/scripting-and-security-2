# Obtener información de la memoria RAM
## Hardware, Memory, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/28/obtener-informacion-de-la-memoria-ram/
```PowerShell
Get-WmiObject win32_physicalmemory | Format-Table Manufacturer,Banklabel,Configuredclockspeed,Devicelocator,Capacity,Serialnumber -autosize

```
