# Ver los programas que se pueden ejecutar por defecto en el router de fibra óptica MitraStar GPT-2541GNAC de Movistar desde PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2018/03/23/ver-los-programas-que-se-pueden-ejecutar-por-defecto-en-el-router-de-fibra-optica-mitrastar-gpt-2541gnac-de-movistar-desde-powershell/
```PowerShell
New-SSHSession -ComputerName 192.168.1.1 -Credential (Get-Credential)
Get-SSHSession
(Invoke-SSHCommand -Index 0 "ls /bin").output

```
