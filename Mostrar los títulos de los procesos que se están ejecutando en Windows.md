# Mostrar los títulos de los procesos que se están ejecutando en Windows
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2018/02/09/mostrar-los-titulos-de-los-procesos-que-se-estan-ejecutando-en-windows/
```PowerShell
Get-Process | Where {$_.MainWindowTitle} | Select-Object ProcessName, MainWindowTitle

```
