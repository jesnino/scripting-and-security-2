# Comunicar dos ordenadores mediante la voz del sistema operativo
## Multimedia, PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2016/01/10/comunicar-dos-ordenadores-mediante-la-voz-del-sistema-operativo/
```PowerShell
#Leer el texto contenido dentro de un fichero mediante la voz del Sistema Operativo
Add-Type -AssemblyName System.Speech
 
gc E:\aleer\fichero.txt | %{
$synthesizer = New-Object -TypeName System.Speech.Synthesis.SpeechSynthesizer
$_
#Establece la velocidad de habla de la SpeechSynthesizer
$synthesizer.Rate=0
$synthesizer.Speak($_)
}

```
```PowerShell
[void][reflection.assembly]::loadwithpartialname(‘system.speech’)
$rec = New-Object ‘System.Speech.Recognition.SpeechRecognitionEngine’
$rec.LoadGrammar((New-Object ‘System.Speech.Recognition.DictationGrammar’))
$rec.SetInputToDefaultAudioDevice()
 
do
{
$rec.Recognize().Text | Out-File e:\wavtext.txt -Append
}while(1)

```
