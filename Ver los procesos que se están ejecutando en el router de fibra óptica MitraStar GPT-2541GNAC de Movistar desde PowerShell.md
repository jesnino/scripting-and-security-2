# Ver los procesos que se están ejecutando en el router de fibra óptica MitraStar GPT-2541GNAC de Movistar desde PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/11/17/ver-los-procesos-que-se-estan-ejecutando-en-el-router-de-fibra-optica-mitrastar-de-movistar-desde-powershell/
```PowerShell
New-SSHSession -ComputerName 192.168.1.1 -Credential (Get-Credential)
Get-SSHSession
(Invoke-SSHCommand -Index 0 "ps").output

```
