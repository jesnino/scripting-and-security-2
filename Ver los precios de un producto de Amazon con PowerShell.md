# Ver los precios de un producto de Amazon con PowerShell
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2017/10/11/ver-los-precios-de-un-producto-de-amazon-con-powershell/
```PowerShell
$web=Invoke-WebRequest 'https://www.amazon.es/Hynix-original-204-pin-PC3L-12800-1600MHz/dp/B00ILWIAEW?th=1'
$web.AllElements | Where Class -eq “a-size-medium a-color-price” | %{$_.innerText}

```
