# Mostrar la posición GPS de los restaurantes más reservados de Madrid
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2018/06/08/mostrar-la-posicion-gps-de-los-restaurantes-mas-reservados-de-madrid/
```PowerShell
$url = "https://www.eltenedor.es/ciudad/madrid/328022"
$result = Invoke-WebRequest $url
#La etiqueta que tenemos buscar es: class="restaurantSelection-name
$restaurantes = $result.AllElements | Where Class -eq “restaurantSelection-name” | %{$_.innerText}

$restaurantes | %{
    $calle = $_
    $ciudad = 'Madrid'
    $urlsi = "https://maps.googleapis.com/maps/api/geocode/json?address=" + $calle + “+” + $ciudad 
    $result = (Invoke-WebRequest -Uri $urlsi).Content | ConvertFrom-JSON
    $posicion = $result.results."geometry".location
    Write-Host $_,$posicion
    Start-Sleep -Seconds 4
}

```
