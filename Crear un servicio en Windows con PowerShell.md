# Crear un servicio en Windows con PowerShell
## PowerShell, Services 
### URL: https://www.jesusninoc.com/2017/10/17/crear-un-servicio-en-windows-con-powershell/
```PowerShell
New-Service -Name "Test" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"

```
