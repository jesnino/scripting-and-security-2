# Ver todos los resultados más relevantes de un producto en Amazon con PowerShell
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2018/03/29/ver-todos-los-resultados-de-un-producto-en-amazon-mostrando-los-resultados-mas-relevantes/
```PowerShell
$web=Invoke-WebRequest 'https://www.amazon.es/s/ref=nb_sb_noss_2?__mk_es_ES=%C3%85M%C3%85%C5%BD%C3%95%C3%91&url=search-alias%3Daps&field-keywords=dron+parrot'
$web.AllElements | Where Class -eq “a-link-normal s-access-detail-page  s-color-twister-title-link a-text-normal” | %{$_.innerText}

```
