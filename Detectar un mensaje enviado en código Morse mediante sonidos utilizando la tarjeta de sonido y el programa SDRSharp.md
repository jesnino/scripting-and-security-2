# Detectar un mensaje enviado en código Morse mediante sonidos utilizando la tarjeta de sonido y el programa SDRSharp
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/04/detectar-un-mensaje-enviado-en-codigo-morse-mediante-sonidos-utilizando-la-tarjeta-de-sonido-y-el-programa-sdrsharp/
```PowerShell
#Morse code
#A|. –
#B|– . . .
#C|– . – .
#Ch|– – – –
#D|– . .
#E|.
#F|. . – .
#G|– – .
#H|. . . .
#I|. .
#J|. – – –
#K|– . –
#L|. – . .
#M|– –
#N|– .
#Ñ|– – . – –
#O|– – –
#P|. – – .
#Q|– – . –
#R|. – .
#S|. . .
#T|–
#U|. . –
#V|. . . –
#W|. – –
#X|– . . –
#Y|– . – –
#Z|– – . .

Get-Content .\textomorse.txt | %{
$letter=$_.split("|")[0]
$morse=$_.split("|")[1]
$values=$morse.split(" ")
Write-Host $letter,$morse
foreach($sound in $values)
{
if($sound -eq ".")
{
#2000 Hz
[console]::beep(2000,500)
}
elseif($sound -eq "–")
{
[console]::beep(2000,800)
}
Start-Sleep -Seconds 1
}
}

```
