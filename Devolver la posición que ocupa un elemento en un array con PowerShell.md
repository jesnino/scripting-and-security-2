# Devolver la posición que ocupa un elemento en un array con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/11/devolver-la-posicion-que-ocupa-un-elemento-en-un-array-con-powershell/
```PowerShell
$dlls = (ls C:\Windows\system32\*.dll).name
[array]::indexof($dlls,"advpack.dll")

```
