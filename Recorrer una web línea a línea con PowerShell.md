# Recorrer una web línea a línea con PowerShell
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2018/06/13/recorrer-una-web-linea-a-linea-con-powershell/
```PowerShell
$web = Invoke-WebRequest "https://www.jesusninoc.com"
$web.Content -split "`n"

```
