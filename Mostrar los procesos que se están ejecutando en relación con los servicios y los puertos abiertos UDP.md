# Mostrar los procesos que se están ejecutando en relación con los servicios y los puertos abiertos UDP
## Network, PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2017/03/03/mostrar-los-procesos-que-se-estan-ejecutando-en-relacion-con-los-servicios-y-los-puertos-abiertos-udp/
```PowerShell
#Mostrar los procesos que se están ejecutando en relación con los servicios y los puertos abiertos UDP
(Get-WmiObject -Class Win32_Service | Where-Object State -EQ 'Running') | %{
Write-Host $_.Name,$_.ProcessId,$_.State,(Get-Process -Id $_.ProcessId).Name,(Get-NetUDPEndpoint | where OwningProcess -EQ $_.ProcessId | select LocalPort,RemoteAddress,RemotePort,OwningProcess)
}

```
