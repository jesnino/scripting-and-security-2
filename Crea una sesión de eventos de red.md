# Crea una sesión de eventos de red
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/04/crea-una-sesion-de-eventos-de-red/
```PowerShell
$timestamp = Get-Date -f yyyy-MM-dd_HH-mm-ss
New-NetEventSession -Name Session1 –LocalFilePath c:\$env:computername-netcap-$timestamp.etl –MaxFileSize 512

```
