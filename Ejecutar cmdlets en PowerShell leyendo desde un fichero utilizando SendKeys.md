# Ejecutar cmdlets en PowerShell leyendo desde un fichero utilizando SendKeys
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2016/12/04/ejecutar-cmdlets-en-powershell-leyendo-desde-un-fichero-utilizando-sendkeys/
```PowerShell
Start-Process powershell_ise
Start-Sleep -Seconds 5

gc .\ejemplo.txt | %{
foreach($letras in [char[]]$_)
{
$letras
[System.Windows.Forms.SendKeys]::SendWait($letras)
Start-Sleep -Milliseconds 500
}
[System.Windows.Forms.SendKeys]::SendWait(" ")
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")
Start-Sleep -Milliseconds 500
}

```
