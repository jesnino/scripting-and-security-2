# Arrancar una aplicación remotamente desde PowerShell teniendo habilitado “Device Portal”
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/27/arrancar-una-aplicacion-remotamente-desde-powershell-teniendo-habilitado-device-portal/
```PowerShell
Invoke-WebRequest -Uri 'http://192.168.1.157:50080/api/taskmanager/app?appid=TWljcm9zb2Z0LkJpbmdXZWF0aGVyXzh3ZWt5YjNkOGJid2UhQXBw' -Method Post

```
