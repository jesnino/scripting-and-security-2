# Switch for a numeric range
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/03/switch-for-a-numeric-range/
```PowerShell
$valor=1001

switch($valor)
{
    {$_ -ge 0 -and $_ -le 1000}{"Poco importante"}
    {$_ -ge 1001 -and $_ -le 10000}{"Algo importante"}
    {$_ -ge 10000 -and $_ -le 100000000}{"Muy importante"}
}

```
