# Mostrar las búsquedas de “El año en búsquedas 2017” mediante PowerShell usando JavaScript (solución 3)
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/09/mostrar-las-busquedas-de-el-ano-en-busquedas-2017-mediante-powershell-usando-javascript-solucion-3/
```PowerShell
$ie = New-Object -comobject InternetExplorer.Application

$ie.Navigate2("https://google.com/trends/embed/yis/2017/GLOBAL/3bc22de5-427e-4737-8e27-f96ee7d75edf?forceMobileMode=false&isPreviewMode=true&hl=es")
 
$ie.Visible = $false

while($ie.ReadyState -ne 4) {start-sleep -m 100}

$ie.document.scripts | % {
    if($_.uniqueNumber -eq 4)
    {
        $_.text,$_.uniqueNumber
        "<script>"+$_.text+"var Items = embedWidgetGlobals.data.listItems; alert(Items)</script>" | Out-File result.html
    }
}

.\result.html

```
