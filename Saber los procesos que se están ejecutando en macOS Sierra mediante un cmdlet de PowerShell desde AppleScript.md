# Saber los procesos que se están ejecutando en macOS Sierra mediante un cmdlet de PowerShell desde AppleScript
## AppleScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/13/saber-los-procesos-que-se-estan-ejecutando-en-macos-sierra-mediante-un-cmdlet-de-powershell-desde-applescript/
```AppleScript
#Listar los procesos que hay en el sistema
set procesos to do shell script "/usr/local/bin/powershell 'Get-Process | Sort-Object -Descending'"
display dialog procesos

```
