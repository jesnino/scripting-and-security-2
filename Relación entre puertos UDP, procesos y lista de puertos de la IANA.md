# Relación entre puertos UDP, procesos y lista de puertos de la IANA
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/11/27/relacion-entre-puertos-udp-procesos-y-lista-de-puertos-de-la-iana/
```PowerShell
#Descargar y guardar el listado de puertos
Invoke-WebRequest 'https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.csv' -OutFile service-names-port-numbers.csv

#Relación entre puertos abiertos UDP y lista de puertos
$portscsv=Import-Csv service-names-port-numbers.csv
$listado=$portscsv | Select-Object 'Service Name','Port Number','Transport Protocol' | Where-Object 'Transport Protocol' -EQ udp
Get-NetUDPEndpoint | %{Write-Host (Get-Process -id $_.OwningProcess).Name, $_.Localaddress, ($listado | Select-Object 'Service Name','Port Number' | Where-Object 'Port Number' -EQ $_.Localport)}

```
