# Leer palabras mediante la voz del Sistema Operativo
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2016/12/15/leer-palabras-mediante-la-voz-del-sistema-operativo/
```PowerShell
Add-Type -AssemblyName System.Speech
 
"hola","casa" | %{
$synthesizer = New-Object -TypeName System.Speech.Synthesis.SpeechSynthesizer
$_
#Establece la velocidad de habla de la SpeechSynthesizer
$synthesizer.Rate=0
$synthesizer.Speak($_)
}

```
