# Comprobar constantemente si está abierto un puerto TCP
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/12/23/comprobar-si-esta-abierto-un-puerto-tcp/
```PowerShell
while(1)
{
    Get-NetTCPConnection | Select-Object LocalAddress,RemotePort,OwningProcess| Where-Object {$_.RemotePort -eq "443"}
    Start-Sleep -Seconds 5
    clear
}

```
