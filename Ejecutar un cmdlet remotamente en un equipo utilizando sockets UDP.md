# Ejecutar un cmdlet remotamente en un equipo utilizando sockets UDP
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/27/ejecutar-un-cmdlet-remotamente-en-un-equipo-utilizando-sockets-udp/
```PowerShell
##Client
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$b=[Text.Encoding]::ASCII.GetBytes('get-process')
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
```PowerShell
##Server
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
$udpclient.Close()
Invoke-Expression ([Text.Encoding]::ASCII.GetString($content))

```
