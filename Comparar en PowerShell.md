# Comparar en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/11/01/comparar-en-powershell/
```PowerShell
#Comparar por nombre de proceso

$data=Get-Process
Start-Process notepad
$data2=Get-Process

Compare-Object -ReferenceObject $data -DifferenceObject $data2 -Property ProcessName -PassThru

```
