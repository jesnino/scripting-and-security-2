# Enviar un fichero BMP (dimensiones 1×1) entre un cliente y un servidor
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/05/20/enviar-un-fichero-bmp-dimensiones-1x1-entre-un-cliente-y-un-servidor/
```PowerShell
function send-msg($file)
{
$client = New-Object System.Net.Sockets.TcpClient "192.168.1.56", 8982
$stream = $client.GetStream()
$writer = New-Object System.IO.StreamWriter $stream

$bytes = [System.IO.File]::ReadAllBytes($file)
$writer.Write($bytes,0,$bytes.length)
$writer.Dispose()
$stream.Dispose()
$client.Dispose()
}

send-msg .\blanco.bmp

```
```PowerShell
$endpoint = new-object System.Net.IPEndPoint ([system.net.ipaddress]::any, 8982)
$listener = new-object System.Net.Sockets.TcpListener $endpoint
$listener.start()

$client = $listener.AcceptTcpClient()
$stream = $client.GetStream();

$reader = New-Object System.IO.StreamReader $stream

$lines=$reader.ReadToEnd()

$enc = [system.Text.Encoding]::Default
$filebytes = $enc.GetBytes($lines)

$contador=$contador+1
[System.IO.File]::WriteAllBytes("recibido.bmp", $filebytes)

$reader.Dispose()
$stream.Dispose()
$client.Dispose()

```
