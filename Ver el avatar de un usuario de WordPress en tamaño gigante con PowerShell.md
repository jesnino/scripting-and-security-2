# Ver el avatar de un usuario de WordPress en tamaño gigante con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/07/ver-el-avatar-de-un-usuario-de-wordpress-en-tamano-gigante-con-powershell/
```PowerShell
$json=(Invoke-WebRequest -Uri 'https://jesusninoc.com/wp-json/wp/v2/users/').content | ConvertFrom-JSON
Start-Process ($json.avatar_urls.96).Replace("s=96","s=800")

```
