# Acceder a las pestañas que están abiertas en Google Chrome con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/25/acceder-a-las-pestanas-que-estan-abiertas-en-google-chrome-con-powershell/
```PowerShell
$url1="https://www.jesusninoc.com"

1..8 | %{
Start-Process chrome.exe -ArgumentList @('-incognito',$url1)
}

Start-Sleep -Seconds 5

1..8 | %{
[System.Windows.Forms.SendKeys]::SendWait('^{'+$_+'}')
Start-Sleep -Seconds 5
}

```
