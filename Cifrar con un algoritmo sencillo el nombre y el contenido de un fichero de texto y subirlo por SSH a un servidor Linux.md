# Cifrar con un algoritmo sencillo el nombre y el contenido de un fichero de texto y subirlo por SSH a un servidor Linux
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/11/13/cifrar-con-un-algoritmo-sencillo-el-nombre-y-el-contenido-de-un-fichero-de-texto-y-subirlo-por-ssh-a-un-servidor-linux/
```PowerShell
#Cifrar el contenido del fichero
$fichero="fichero.txt"
$cifrado=gc $fichero
$clavecifrado=1
$textocifrado=(0..($cifrado.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($cifrado[$_].ToString(),0)+$clavecifrado)}) -join ""

#Cifrar el nombre y añadir el contenido cifrado
#Quitamos los puntos y otros caracteres para no tener errores a la hora de crear el nuevo fichero cifrado
$ficherosin=$fichero.Replace(".","")
$ficherocifrado=(0..($ficherosin.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($ficherosin[$_].ToString(),0)+$clavecifrado)}) -join ""
$textocifrado | Out-File $ficherocifrado

#Subir un fichero por SSH a un servidor Linux desde PowerShell en Windows
Set-SCPFile -LocalFile $ficherocifrado -ComputerName 192.168.1.162 -RemotePath . -Credential (Get-Credential)

```
