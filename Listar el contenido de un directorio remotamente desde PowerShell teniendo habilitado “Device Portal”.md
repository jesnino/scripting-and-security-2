# Listar el contenido de un directorio remotamente desde PowerShell teniendo habilitado “Device Portal”
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/10/01/listar-el-contenido-de-un-directorio-remotamente-desde-powershell-teniendo-habilitado-device-portal/
```PowerShell
$result=Invoke-WebRequest -Uri 'http://192.168.1.157:50080/api/filesystem/apps/files?knownfolderid=CameraRoll&packagefullname=%5C&path=%5C&_=1505494324049' -Method get
$result.content

```
