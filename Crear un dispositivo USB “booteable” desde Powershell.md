# Crear un dispositivo USB “booteable” desde Powershell
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2016/12/05/crear-un-dispositivo-usb-booteable-desde-powershell/
```PowerShell
#Realizado por Adrián García
Mount-DiskImage –ImagePath “C:\Users\adria\Desktop\Carpeta\Win10 Pro.iso”
Get-Disk
Clear-Disk –Number 1 -RemoveData
New-Partition -DiskNumber 1 -UseMaximumSize -AssignDriveLetter -IsActive:$true
Format-Volume –FileSystem NTFS –DriveLetter D
bootsect.exe /NT60 D:
Copy-Item –Recurse F:\* D:\

```
