# Cifrar de forma sencilla el libro “El ingenioso hidalgo Don Quijote de la Mancha” con PowerShell (parte 8)
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/30/cifrar-de-forma-sencilla-el-libro-el-ingenioso-hidalgo-don-quijote-de-la-mancha-con-powershell-parte-8/
```PowerShell
$var=5

ForEach ($elemento in gc .\quijote.txt){
(0..($elemento.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($elemento[$_].ToString(),0)+$var)}) -join "" | Out-File quijotecif.txt -Append
}

```
