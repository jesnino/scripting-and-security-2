# Generar letras aleatorias
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/11/generar-letras-aleatorias/
```PowerShell
((65..90) + (97..122) | Get-Random -Count 1 |  % {[char]$_})

```
