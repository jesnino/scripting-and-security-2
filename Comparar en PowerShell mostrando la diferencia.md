# Comparar en PowerShell mostrando la diferencia
## PowerShell 
### URL: https://www.jesusninoc.com/2017/11/15/comparar-en-powershell-mostrando-la-diferencia/
```PowerShell
$data=Get-Process
Start-Process notepad
$data2=Get-Process

Compare-Object -ReferenceObject $data -DifferenceObject $data2 -Property ProcessName -PassThru | Sort-Object -Property ProcessName | Select-Object -Property ProcessName, Id, SideIndicator

```
