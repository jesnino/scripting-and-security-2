# Habilitar BitLocker en un disco virtual
## PowerShell, Virtualization 
### URL: https://www.jesusninoc.com/2017/10/20/habilitar-bitlocker-en-un-disco-virtual/
```PowerShell
#Crear disco virtual en la unidad d
New-VHD –Path d:\disc.vhdx –SizeBytes 1GB
#Montar disco virtual
Mount-VHD –Path d:\disc.vhdx
#Habilitar BitLocker para la unidad montada anteriormente (por ejemplo unidad e)
Enable-BitLocker -MountPoint "e:" -RecoveryPasswordProtector -UsedSpaceOnly -Verbose

```
