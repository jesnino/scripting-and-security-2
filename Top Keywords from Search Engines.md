# Top Keywords from Search Engines
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/01/02/top-keywords-from-search-engines/
```PowerShell
$web=Invoke-WebRequest 'https://www.alexa.com/siteinfo/google.es'
$web.AllElements | Where class -eq “topkeywordellipsis” | %{$_.innerText}

```
