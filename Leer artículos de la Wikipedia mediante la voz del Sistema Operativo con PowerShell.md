# Leer artículos de la Wikipedia mediante la voz del Sistema Operativo con PowerShell
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/03/22/leer-articulos-de-la-wikipedia-mediante-la-voz-del-sistema-operativo-con-powershell/
```PowerShell
Add-Type -AssemblyName System.Speech
$synthesizer = New-Object -TypeName System.Speech.Synthesis.SpeechSynthesizer
$synthesizer.SelectVoice("Microsoft Zira Desktop")
$synthesizer.Rate=0

$json=Invoke-WebRequest -Uri 'https://en.wikipedia.org/w/api.php?action=parse&format=json&prop=text&page=PowerShell' | ConvertFrom-JSON
 
$json.parse.text.'*' -replace "<.*?>" | %{
$synthesizer.Speak($_)
}

```
