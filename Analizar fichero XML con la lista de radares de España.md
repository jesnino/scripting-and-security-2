# Analizar fichero XML con la lista de radares de España
## PowerShell 
### URL: https://www.jesusninoc.com/2018/02/17/analizar-fichero-xml-con-la-lista-de-radares-de-espana/
```PowerShell
$radares = [XML](Invoke-WebRequest "http://www.dgt.es/images/Tramos_INVIVE_12042017.xml").content

[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList

$radares.RAIZ.PROVINCIA.CARRETERA | %{
    $radar = $_.DENOMINACION + "|" + $_.RADAR.PUNTO_INICIAL.PK
    [void]$arraylist.Add($radar)
}

$arraylist | Sort-Object

```
