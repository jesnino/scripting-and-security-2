# Convertir a binario las direcciones MAC de los dispositivos de red
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/25/convertir-a-binario-las-direcciones-mac-de-los-dispositivos-de-red/
```PowerShell
ForEach($val in ((Get-NetAdapter).MacAddress).replace("-",""))
{
$val
0..($val.Length-1) | %{
Write-Host $val[$_],([Convert]::ToString([Byte]::Parse($val[$_],[System.Globalization.NumberStyles]::HexNumber),2))
}
}

```
