# Hacking wifi with Powershell
## Network, PowerShell, Wireless 
### URL: https://www.jesusninoc.com/2015/02/11/hacking-wifi-with-powershell/
```PowerShell
(netsh wlan show interface | Select-String SSID)[0] | %{
[String]$SSID=$_
$SSID=$SSID.replace("SSID","").replace(":","").trim()
$SSID
netsh wlan show profile name=$SSID key=clear | Select-String 'Contenido de la clave'
}

```
