# Utilizar el fichero JSON obtenido de la función Autocompletar de Google
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/05/07/utilizar-el-fichero-json-obtenido-de-la-funcion-autocompletar-de-google/
```PowerShell
$json=(Invoke-WebRequest -Uri 'https://www.google.es/complete/search?client=hp&hl=es&gs_rn=64&gs_ri=hp&cp=11&gs_id=2f&q=powershell%20&xhr=t').content | ConvertFrom-JSON
$json | %{$_}

```
