# Escribir y ver un evento en el registro de eventos de aplicación
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/04/escribir-y-ver-un-evento-en-el-registro-de-eventos-de-aplicacion/
```PowerShell
Write-EventLog -LogName "Application" -Source "Microsoft-Windows-User-Loader" -EventID 916 -EntryType Information -Message "Mensaje ejemplo" -Category 2 -RawData 10,20

Get-EventLog -LogName "Application" -Source "Microsoft-Windows-User-Loader"

```
