# Ver categorías de WordPress JSON API desde PowerShell
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/03/08/ver-categorias-de-wordpress-json-api-desde-powershell/
```PowerShell
$json=(Invoke-WebRequest -Uri 'https://www.jesusninoc.com/wp-json/wp/v2/categories').content | ConvertFrom-JSON
$json.name

```
