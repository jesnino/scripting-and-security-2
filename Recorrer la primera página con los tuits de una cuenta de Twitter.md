# Recorrer la primera página con los tuits de una cuenta de Twitter
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/11/22/recorrer-la-primera-pagina-con-los-tuits-de-una-cuenta-de-twitter/
```PowerShell
$web = Invoke-WebRequest "https://twitter.com/search?f=tweets&vertical=default&lang=en&q=from%3Amicrosoft"
$web.AllElements | Where Class -eq “TweetTextSize  js-tweet-text tweet-text” | %{$_.innerText}

```
