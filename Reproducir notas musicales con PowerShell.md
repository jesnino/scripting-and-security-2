# Reproducir notas musicales con PowerShell
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/23/reproducir-notas-musicales-con-powershell/
```PowerShell
#Genera tonos simples en el altavoz

#Función Beep 
#Beep(Frecuencia,Duración)
 
#Freq: la frecuencia del sonido, en hertz
#Duración: duración del sonido, en milisegundos

#Frecuencias notas 4ª octava
#Do4	261,625565 Hz
#Re4	293,664768 Hz
#Mi4	329,627557 Hz
#Fa4	349,228231 Hz
#Sol4	391,995436 Hz
#La4	440,000000 Hz
#Si4	493,883301 Hz

[System.Console]::Beep(261,500)
[System.Console]::Beep(293,500)
[System.Console]::Beep(329,500)
[System.Console]::Beep(349,500)
[System.Console]::Beep(391,500)
[System.Console]::Beep(440,500)
[System.Console]::Beep(493,500)

```
