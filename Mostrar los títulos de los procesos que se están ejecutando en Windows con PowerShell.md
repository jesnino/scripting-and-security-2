# Mostrar los títulos de los procesos que se están ejecutando en Windows con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/15/mostrar-los-titulos-de-los-procesos-que-se-estan-ejecutando-en-windows-con-powershell/
```PowerShell
Get-Process | Where {$_.MainWindowTitle} | Select-Object ProcessName, MainWindowTitle

```
