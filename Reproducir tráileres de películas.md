# Reproducir tráileres de películas
## Automation, Multimedia, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/11/21/reproducir-traileres-de-peliculas/
```PowerShell
$url='https://www.youtube.com/user/UniversalSpain/playlists?sort=lad&flow=list&view=1'
$result = Invoke-WebRequest $url
#Respetar los dos espacios entre "link yt"
$result.AllElements | Where class -eq “ spf-link  yt-uix-sessionlink” | %{$_.outerText
'https://www.youtube.com'+$_.href
#Reproducir tráiler
$trailer='https://www.youtube.com'+$_.href
Start-Process chrome $trailer
Start-Sleep -Seconds 10
}

```
