# Relación entre puertos UDP y procesos
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/22/relacion-entre-puertos-udp-y-procesos/
```PowerShell
Get-NetUDPEndpoint | %{Write-Host (Get-Process -id $_.OwningProcess).Name,$_.LocalAddress,$_.LocalPort}

```
