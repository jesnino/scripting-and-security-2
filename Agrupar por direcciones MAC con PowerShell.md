# Agrupar por direcciones MAC con PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2018/04/14/agrupar-por-direcciones-mac-con-powershell/
```PowerShell
Get-NetNeighbor | Group-Object LinkLayerAddress

```
