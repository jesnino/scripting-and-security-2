# Relación entre IP, puertos y procesos con PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2018/04/13/relacion-entre-ip-puertos-y-procesos-con-powershell/
```PowerShell
Get-NetTCPConnection | %{Write-Host $_.LocalAddress,$_.LocalPort,$_.RemoteAddress,$_.RemotePort,$_.OwningProcess,(Get-Process -id $_.OwningProcess).Name}

```
