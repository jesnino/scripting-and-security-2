# Cifrar con un algoritmo sencillo el nombre y el contenido de un fichero de texto (enviar la clave utilizada en el algoritmo mediante una petición web a un servidor)
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/05/16/cifrar-con-un-algoritmo-sencillo-el-nombre-y-el-contenido-de-un-fichero-de-texto-enviar-la-clave-utilizada-en-el-algoritmo-mediante-una-peticion-web-a-un-servidor/
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

$clavecifrado

Invoke-WebRequest "https://www.jesusninoc.com/clave/$clavecifrado"

```
