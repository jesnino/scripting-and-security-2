# Letras minúsculas a MD5
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/23/letras-minusculas-a-md5/
```PowerShell
[Reflection.Assembly]::LoadWithPartialName("System.Web")
#Listar letras de la a a la z
[char]'a'..[char]'z' | %{
#ASCII code to MD5
[System.Web.Security.FormsAuthentication]::HashPasswordForStoringInConfigFile([char]$_, "MD5")
}

```
