# Poner a 1 el cuarto bit en una cadena de bits
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/06/poner-a-1-el-cuarto-bit-en-una-cadena-de-bits/
```PowerShell
$decimal = 32
[Convert]::ToString($decimal, 2)

$bit = 3
$decimal = $decimal -bor [Math]::Pow(2, $bit)
[Convert]::ToString($decimal, 2)

```
