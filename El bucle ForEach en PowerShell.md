# El bucle ForEach en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/10/el-bucle-foreach-en-powershell/
```PowerShell
$numeros=1..5
$numeros | %{$PSItem}
$numeros | %{$_}
foreach($numero in $numeros)
{
$numero
}

```
