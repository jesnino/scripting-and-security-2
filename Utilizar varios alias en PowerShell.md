# Utilizar varios alias en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/04/15/utilizar-varios-alias-en-powershell/
```PowerShell
function Get-Listados
{
    [Alias('listar','lista','listas')]
    [CmdletBinding()]
    param()
 
    Get-ChildItem
}

```
