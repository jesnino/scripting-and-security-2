# Ejecutar un script de PowerShell en Linux realizando una conexión SSH desde PowerShell en Windows
## PowerShell 
### URL: https://www.jesusninoc.com/2017/09/26/ejecutar-un-script-de-powershell-en-linux-realizando-una-conexion-ssh-desde-powershell-en-windows/
```PowerShell
New-SSHSession -ComputerName 192.168.1.162 -Credential (Get-Credential)
Invoke-SSHCommand -Index 0 "pwd"
Invoke-SSHCommand -Index 0 "cat script.ps1"
Invoke-SSHCommand -Index 0 "powershell script.ps1"

```
