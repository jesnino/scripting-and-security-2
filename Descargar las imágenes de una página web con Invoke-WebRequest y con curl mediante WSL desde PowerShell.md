# Descargar las imágenes de una página web con Invoke-WebRequest y con curl mediante WSL desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/27/descargar-las-imagenes-de-una-pagina-web-con-invoke-webrequest-y-con-curl-mediante-wsl-desde-powershell/
```PowerShell
$url = "https://www.jesusninoc.com/2018/05/13/get-rss-feed-from-jesusninoc-com-new-version/"
$result = Invoke-WebRequest $url
$result.Images.src

$result.Images.src | %{
    wsl curl -O $_
}

```
