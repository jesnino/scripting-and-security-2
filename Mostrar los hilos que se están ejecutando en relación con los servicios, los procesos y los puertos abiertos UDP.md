# Mostrar los hilos que se están ejecutando en relación con los servicios, los procesos y los puertos abiertos UDP
## Network, PowerShell, Processes, Services, Threads 
### URL: https://www.jesusninoc.com/2017/03/11/mostrar-los-hilos-que-se-estan-ejecutando-en-relacion-con-los-servicios-los-procesos-y-los-puertos-abiertos-udp/
```PowerShell
#Mostrar los hilos que se están ejecutando en relación con los servicios, los procesos y los puertos abiertos UDP
$i=0
(Get-WmiObject -Class Win32_Thread) | %{
$i++
Write-Host $i,$_.Handle,$_.ProcessHandle,(Get-WmiObject -Class Win32_Service | Where-Object State -EQ ‘Running’ | Where-Object ProcessId -EQ $_.ProcessHandle),(Get-Process -Id $_.ProcessHandle).ProcessName
Write-Host (Get-Process -Id $_.ProcessHandle).ProcessName,(Get-NetUDPEndpoint | where OwningProcess -EQ $_.ProcessHandle | select LocalPort,RemoteAddress,RemotePort,OwningProcess)
}

```
