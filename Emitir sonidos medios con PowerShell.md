# Emitir sonidos medios con PowerShell
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/16/emitir-sonidos-medios-con-powershell/
```PowerShell
#Beep function
#Generates simple tones on the speaker

#Beep(Freq,Duration)
#Beep(Frecuencia,Duración)

#Freq: The frequency of the sound, in hertz
#Duration: The duration of the sound, in milliseconds

#Frecuencias en la zona "media" del espectro (256Hz - 2000Hz)
[System.Console]::Beep(256,100)
[System.Console]::Beep(500,100)
[System.Console]::Beep(1000,100)
[System.Console]::Beep(1999,100)

```
