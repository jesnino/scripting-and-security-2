# Iniciar cinco trabajos en segundo plano con PowerShell
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2017/02/09/iniciar-cinco-trabajos-en-segundo-plano-con-powershell/
```PowerShell
1..5 | %{Start-Job -ScriptBlock {Get-Process}}

1..5 | %{Start-Job -ScriptBlock {Get-Date | out-file horas.txt -Append}}

```
