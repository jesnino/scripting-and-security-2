# Enviar un mensaje entre un cliente y dos servidores mediante datagramas (UDP)
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/08/29/enviar-un-mensaje-entre-un-cliente-y-dos-servidores-mediante-datagramas-udp/
```PowerShell
##Server 1
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
[Text.Encoding]::ASCII.GetString($content)

```
```PowerShell
##Server 2
$port=2022
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
[Text.Encoding]::ASCII.GetString($content)

```
```PowerShell
##Client
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$val=date
$b=[Text.Encoding]::ASCII.GetBytes($val.ToString())
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()
$port=2022
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$val=date
$b=[Text.Encoding]::ASCII.GetBytes($val.ToString())
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
