# Convertir la entrada de micrófono a texto
## Automation, Multimedia, PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2016/12/26/convertir-la-entrada-de-microfono-a-texto/
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
