# Analizar información de red (protocolo TCP)
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/04/26/analizar-informacion-de-red-protocolo-tcp/
```PowerShell
#Relación entre IP, puertos y procesos
Get-NetTCPConnection | %{Write-Host $_.LocalAddress,$_.LocalPort,$_.RemoteAddress,$_.RemotePort,$_.OwningProcess,(Get-Process -id $_.OwningProcess).Name}

#Agrupar IP
((Get-NetTCPConnection | Select-Object RemoteAddress).RemoteAddress | Group-Object).Name

#Agrupar IP y quitar las que no son necesarias
(((Get-NetTCPConnection | Select-Object RemoteAddress).RemoteAddress | Group-Object).Name) | Where-Object {$_ -notcontains "::" -and $_ -notcontains "0.0.0.0"}

```
