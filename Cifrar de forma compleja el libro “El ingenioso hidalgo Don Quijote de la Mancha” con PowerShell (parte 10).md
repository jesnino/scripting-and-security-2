# Cifrar de forma compleja el libro “El ingenioso hidalgo Don Quijote de la Mancha” con PowerShell (parte 10)
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/02/04/cifrar-de-forma-compleja-el-libro-el-ingenioso-hidalgo-don-quijote-de-la-mancha-con-powershell-parte-10/
```PowerShell
#Cifrar incrementando un valor a cada letra (el valor empieza en 0 y va sumando 1) de cada palabra de cada frase
$var=0
ForEach ($frases in gc .\quijote.txt){
$frasec=""
ForEach ($palabra in $frases.split()){
$frasecn=(0..($palabra.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($palabra[$_].ToString(),0)+($var=$var+1))}) -join ""
$frasec=$frasec+$frasecn
$var=0
}
$frasec | Out-File quijotecifcomplex.txt -Append
}

```
