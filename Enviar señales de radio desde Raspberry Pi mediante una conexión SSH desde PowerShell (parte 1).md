# Enviar señales de radio desde Raspberry Pi mediante una conexión SSH desde PowerShell (parte 1)
## PowerShell, Radio 
### URL: https://www.jesusninoc.com/2018/02/20/enviar-senales-de-radio-desde-raspberry-pi-mediante-una-conexion-ssh-desde-powershell-parte-1/
```PowerShell
#Crear un audio que vamos a mandar mediante señales de radio
#Convertir una frase en audio con la voz del sistema operativo desde PowerShell

Add-Type -AssemblyName System.Speech

$synthesizer = New-Object -TypeName System.Speech.Synthesis.SpeechSynthesizer
$synthesizer.SetOutputToWaveFile("saludo.wav")
$synthesizer.Speak("Hola amigo Pedro")
$synthesizer.SetOutputToDefaultAudioDevice()
Get-ChildItem .\saludo.wav

```
