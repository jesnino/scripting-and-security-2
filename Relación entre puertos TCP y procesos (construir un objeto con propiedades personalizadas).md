# Relación entre puertos TCP y procesos (construir un objeto con propiedades personalizadas)
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/03/relacion-entre-puertos-tcp-y-procesos-construir-un-objeto-con-propiedades-personalizadas/
```PowerShell
Get-NetTCPConnection | Select-Object LocalAddress,LocalPort,OwningProcess,@{n='Nombre proceso';e={Get-Process -id ($_ | Select-Object -ExpandProperty OwningProcess) | Select-Object -ExpandProperty Name}}

```
