# Ejecutar un cmdlet de PowerShell desde AppleScript
## AppleScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/08/ejecutar-un-cmdlet-de-powershell-desde-applescript/
```AppleScript
#Listar los ficheros que hay en una carpeta
set ficheros to do shell script "/usr/local/bin/powershell Get-ChildItem /Users/lamac"
display dialog ficheros

```
