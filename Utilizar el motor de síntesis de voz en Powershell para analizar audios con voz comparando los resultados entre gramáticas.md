# Utilizar el motor de síntesis de voz en Powershell para analizar audios con voz comparando los resultados entre gramáticas
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2017/12/27/utilizar-el-motor-de-sintesis-de-voz-en-powershell-para-analizar-audios-con-voz-comparando-los-resultados-entre-gramaticas/
```PowerShell
#Guardar en un fichero de audio un texto pronunciado mediante el motor de síntesis de voz en PowerShell

#Cargar el espacio de nombres System.Speech que contiene los tipos que admiten el reconocimiento de voz
[void][System.Reflection.Assembly]::LoadWithPartialName("System.Speech")

#Crear un objeto de tipo motor de síntesis de voz
$speaker = [System.Speech.Synthesis.SpeechSynthesizer]::new()

#Configurar el motor de síntesis de voz para guardar en un fichero de audio
$speaker.SetOutputToWaveFile("saludos2.wav")

#Pronunciar el texto
$speaker.Speak("Hola, hola. ¿Qué tal estás? ¿Qué edad tienes? ¿Tienes novia?")

#Configurar el motor de síntesis de voz para enviar el resultado en el dispositivo de audio predeterminado
$speaker.SetOutputToDefaultAudioDevice()

```
```PowerShell
#Cargar los espacios de nombres System.Speech que contienen los tipos que admiten el reconocimiento de voz
[void][System.Reflection.Assembly]::LoadWithPartialName("System.Speech")

#Crear un objeto de tipo motor de síntesis de voz que permite a PowerShell escuchar voz para una gramática de reconocimiento de voz utilizada para el dictado de texto sin formato
$speechRecogEng = [System.Speech.Recognition.SpeechRecognitionEngine]::new()
#Crear un objeto de tipo motor de síntesis de voz que permite a PowerShell escuchar voz para una gramática con restricciones
$speechRecogEngRestr = [System.Speech.Recognition.SpeechRecognitionEngine]::new()

#Representar una gramática de reconocimiento de voz utilizada para el dictado de texto sin formato
$speechRecogEng.LoadGrammar([System.Speech.Recognition.DictationGrammar]::new())
#Crear las restricciones para una gramática de reconocimiento de voz
$speechRecogEngRestr.LoadGrammar([System.Speech.Recognition.GrammarBuilder]::new("hola"))
$speechRecogEngRestr.LoadGrammar([System.Speech.Recognition.GrammarBuilder]::new("tal"))
$speechRecogEngRestr.LoadGrammar([System.Speech.Recognition.GrammarBuilder]::new("novia"))
$speechRecogEngRestr.LoadGrammar([System.Speech.Recognition.GrammarBuilder]::new("edad"))

#Configurar los motores de síntesis de voz para recibir la entrada desde un archivo de formato de sonido (.wav)
$speechRecogEng.SetInputToWaveFile(".\saludos2.wav")
$speechRecogEngRestr.SetInputToWaveFile(".\saludos2.wav")

do{
#Inicia una operación de reconocimiento de voz sincrónico
$recognize=$speechRecogEng.Recognize()
#Confidente: obtiene un valor, asignado por el reconocedor, que representa la probabilidad de coincidencia de RecognizedPhrase con una entrada determinada
"Sin restricciones",$recognize.Text,$recognize.Confidence
$recognizeRestr=$speechRecogEngRestr.Recognize()
"Con restricciones",$recognizeRestr.Text,$recognizeRestr.Confidence
Start-Sleep -Seconds 2
#Mientras que haya audio
}while($speechRecogEng.AudioFormat)

```
