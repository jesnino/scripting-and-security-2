# URLs have been captured for this domain (The Wayback Machine)
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/05/19/urls-have-been-captured-for-this-domain-the-wayback-machine/
```PowerShell
$url="https://web.archive.org/web/*/https://jesusninoc.com/*"
$result = Invoke-WebRequest $url
$result.AllElements | Where class -eq "odd" | %{$_.innerText}

```
