# Línea de comando utilizada para iniciar un proceso
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/28/linea-de-comando-utilizada-para-iniciar-un-proceso/
```PowerShell
Get-WmiObject -Class win32_process | select name, CommandLine

```
