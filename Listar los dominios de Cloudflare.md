# Listar los dominios de Cloudflare
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/03/05/listar-los-dominios-de-cloudflare/
```PowerShell
#Listado los dominios de Cloudflare, Inc. que aparecen en la primera página en Netcraft
[String]$resultado=(Invoke-WebRequest "https://toolbar.netcraft.com/netblock?q=CLOUDFLARENET,104.16.0.0,104.31.255.255").AllElements.href | Select-String "site_report" | Select-String "https://" | Select-String -NotMatch "#"
$resultado.replace("/site_report?url=","").split(" ")

```
