# Ver la popularidad de Google según Alexa
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/05/29/ver-la-popularidad-de-google-segun-alexa/
```PowerShell
((Invoke-WebRequest "https://www.alexa.com/siteinfo/google.com").AllElements | Where class -eq “metrics-data align-vmiddle”)[0].innerText

```
