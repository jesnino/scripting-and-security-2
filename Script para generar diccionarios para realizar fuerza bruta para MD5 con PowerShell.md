# Script para generar diccionarios para realizar fuerza bruta para MD5 con PowerShell
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/23/script-para-generar-diccionarios-para-realizar-fuerza-bruta-para-md5-con-powershell/
```PowerShell
[Reflection.Assembly]::LoadWithPartialName("System.Web")

gc .\diccionario.txt | %{
$_+","+([System.Web.Security.FormsAuthentication]::HashPasswordForStoringInConfigFile($_, "MD5")) | Out-File -Append diccionariofuerza.txt
}

```
```PowerShell
[Reflection.Assembly]::LoadWithPartialName("System.Web")
#Listar letras de la a a la z
[Char]'a'..[Char]'z' | %{
[Char]$_+","+([System.Web.Security.FormsAuthentication]::HashPasswordForStoringInConfigFile([Char]$_, "MD5")) | Out-File -Append diccionariofuerza.txt
}

```
```PowerShell
[Reflection.Assembly]::LoadWithPartialName("System.Web")
#Listar letras de la A a la Z
[Char]'A'..[Char]'Z' | %{
[Char]$_+","+([System.Web.Security.FormsAuthentication]::HashPasswordForStoringInConfigFile([Char]$_, "MD5")) | Out-File -Append diccionariofuerza.txt
}

```
