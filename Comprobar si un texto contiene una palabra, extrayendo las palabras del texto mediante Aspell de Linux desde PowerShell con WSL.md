# Comprobar si un texto contiene una palabra, extrayendo las palabras del texto mediante Aspell de Linux desde PowerShell con WSL
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/27/comprobar-si-un-texto-contiene-una-palabra-extrayendo-las-palabras-del-texto-mediante-aspell-de-linux-desde-powershell-con-wsl/
```PowerShell
(gc .\corregir.txt).Split(" ").ToLower() | bash -c 'aspell list --encoding iso-8859-1' | Group-Object | Where-Object {$_.Name -match "aquarius"}

```
