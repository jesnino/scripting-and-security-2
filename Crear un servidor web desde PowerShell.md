# Crear un servidor web desde PowerShell
## Network, PowerShell, Servers, Web 
### URL: https://www.jesusninoc.com/2018/06/03/crear-un-servidor-web-desde-powershell/
```PowerShell
$routes = @{
    "/" = { return '<html><body>Servidor web</body></html>' }
}

$url = 'https://localhost:8080/'
$listener = New-Object System.Net.HttpListener
$listener.Prefixes.Add($url)
$listener.Start()

Write-Host "Funcionando $url..."

while ($listener.IsListening)
{
    $context = $listener.GetContext()
    $requestUrl = $context.Request.Url
    $con
    $response = $context.Response

    Write-Host ''
    Write-Host "Petición: $requestUrl"

    $localPath = $requestUrl.LocalPath
    $route = $routes.Get_Item($requestUrl.LocalPath)

    if ($route -eq $null)
    {
        $response.StatusCode = 404
    }
    else
    {
        $content = & $route
        $buffer = [System.Text.Encoding]::UTF8.GetBytes($content)
        $response.ContentLength64 = $buffer.Length
        $response.OutputStream.Write($buffer, 0, $buffer.Length)
    }
    
    $response.Close()

    $responseStatus = $response.StatusCode
    Write-Host "Respuesta: $responseStatus"
}

```
