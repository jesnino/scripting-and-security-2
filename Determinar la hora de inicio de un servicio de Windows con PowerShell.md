# Determinar la hora de inicio de un servicio de Windows con PowerShell
## PowerShell, Services 
### URL: https://www.jesusninoc.com/2018/01/31/determinar-la-hora-de-inicio-de-un-servicio-de-windows-con-powershell/
```PowerShell
Get-WmiObject -ClassName Win32_Service -PipelineVariable Servicio | %{
    Get-Process -Id $_.ProcessId | 
    Select-Object -Property @{label='NameService';expression={$Servicio.Name}},StartTime,@{label='NameProcess';expression={$_.Name}} |
    Format-Custom
    }

```
