# Crear y ejecutar un script en el router de fibra óptica MitraStar GPT-2541GNAC de Movistar desde PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2018/03/18/crear-y-ejecutar-un-script-en-el-router-de-fibra-optica-mitrastar-gpt-2541gnac-de-movistar-desde-powershell/
```PowerShell
New-SSHSession -ComputerName 192.168.1.1 -Credential (Get-Credential)
Get-SSHSession
(Invoke-SSHCommand -Index 0 "echo 'echo hola' >> /var/script1.sh").output
(Invoke-SSHCommand -Index 0 "sh /var/script1.sh").output

```
