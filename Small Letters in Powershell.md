# Small Letters in Powershell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/01/31/small-letters-in-powershell/
```PowerShell
[char]'a'..[char]'z' | %{[char]$_}

97..122 | %{[char]$_}

```
