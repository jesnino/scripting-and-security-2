# Obtener información sobre el comando ejecutado analizando procesos con una llamada WMI
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/11/09/obtener-informacion-sobre-el-comando-ejecutado-analizando-procesos-con-una-llamada-wmi/
```PowerShell
Get-WmiObject -Class win32_process | select Path, ExecutablePath, CommandLine | Format-Custom

```
