# Encontrar cmdlets en un bloque de PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/06/22/encontrar-cmdlets-en-un-bloque-de-powershell/
```PowerShell
$code = {
    Get-Process
    Get-Service
    $var2 = 12
}
$code.Ast.FindAll( { $true }, $true) | Where-Object { $_.GetType().Name -eq 'CommandAst' } | select CommandElements

```
