# Ver la tabla de direcciones ARP asociadas a un router de fibra óptica MitraStar GPT-2541GNAC de Movistar con PowerShell
## Automation, Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/03/13/ver-la-tabla-de-direcciones-arp-asociadas-a-un-router-de-fibra-optica-mitrastar-de-movistar-con-powershell/
```PowerShell
$user="1234"
$pass="1234"
$pair="${user}:${pass}"
$bytes=[System.Text.Encoding]::ASCII.GetBytes($pair)
$base64=[System.Convert]::ToBase64String($bytes)
$basicAuthValue="$base64"
$headers=@{sessionKey=$basicAuthValue;pass=""}

$url='http://192.168.1.1/login-login.cgi'
$result=(Invoke-WebRequest -Uri $url -Method POST -Headers $headers -SessionVariable login)

$url='http://192.168.1.1/arpview.cmd'
$result=(Invoke-WebRequest -Uri $url -Method GET -WebSession $login)
($result.AllElements).outerText

```
