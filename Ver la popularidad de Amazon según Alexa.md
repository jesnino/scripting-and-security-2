# Ver la popularidad de Amazon según Alexa
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/04/23/ver-la-popularidad-de-amazon-segun-alexa/
```PowerShell
((Invoke-WebRequest "https://www.alexa.com/siteinfo/amazon.com").AllElements | Where class -eq “metrics-data align-vmiddle”)[0].innerText

```
