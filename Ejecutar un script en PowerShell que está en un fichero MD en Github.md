# Ejecutar un script en PowerShell que está en un fichero MD en Github
## PowerShell 
### URL: https://www.jesusninoc.com/2018/06/17/ejecutar-un-script-en-powershell-que-esta-en-un-fichero-md-en-github/
```PowerShell
# Invoke-WebRequest : Anulada la solicitud: No se puede crear un canal seguro SSL/TLS
# https://www.jesusninoc.com/2018/02/19/invoke-webrequest-anulada-la-solicitud-no-se-puede-crear-un-canal-seguro-ssl-tls/

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

$url="https://github.com/jesusninoc/scripting-and-security-1/blob/master/Acortar%20una%20frase.md"
$result = Invoke-WebRequest $url

# Buscar el div class que tiene el script
# $result.AllElements | Where Class -Match “highlight highlight” | %{$_.innerText} | iex
$result.AllElements | Where Class -Match "highlight highlight-source-powershell" | %{$_.innerText} | iex

```
