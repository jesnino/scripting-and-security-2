# Tabla de caracteres Base64
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/11/tabla-de-caracteres-base64/
```PowerShell
#Array que va a contener todos los caracteres en Base64
$arrayBase64=""
#Añadir al array las mayúsculas
$arrayBase64+=[char]'A'..[char]'Z' | %{[char]$_}
#Añadir al array las minúsculas
$arrayBase64+=[char]'a'..[char]'z' | %{[char]$_}
#Añadir al array los números
$arrayBase64+=[char]'0'..[char]'9' | %{[char]$_}
#Añadir al array el carácter + y /
$arrayBase64+="+"
$arrayBase64+="/"
#Quitar los espacios del array
$arrayBase64=$arrayBase64-replace " "
#Mostrar los caracteres
$arrayBase64
#Número de caracteres en Base64
$arrayBase64.Length
#Primer carácter
$arrayBase64[0]
#Último carácter
$arrayBase64[$arrayBase64.Length-1]

```
