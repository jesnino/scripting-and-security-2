# Crear y ejecutar un script de Bash realizando una conexión SSH desde PowerShell en Windows
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/22/crear-y-ejecutar-un-script-de-bash-realizando-una-conexion-ssh-desde-powershell-en-windows/
```PowerShell
New-SSHSession -ComputerName 192.168.1.162 -Credential (Get-Credential) -Force
Invoke-SSHCommand -Index 0 'echo "echo hola" > script3.sh'
Invoke-SSHCommand -Index 0 "cat script3.sh"
Invoke-SSHCommand -Index 0 "sh script3.sh"

```
