# Leer el contenido de un fichero que contiene bits
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/15/leer-el-contenido-de-un-fichero-que-contiene-bits/
```PowerShell
gc .\blanco.bmp

#Leer el contenido del fichero BMP blanco en decimal y representar cada símbolo decimal en hexadecimal
Write-Host "Contenido del fichero BMP blanco en hexadecimal"

$val=[System.IO.File]::ReadAllBytes('blanco.bmp')
0..($val.Length-1) | %{
    $cadenah=[System.String]::Format("{0:X}", [System.Convert]::ToUInt32($val[$_]))
    Write-Host $cadenah " " -NoNewline
}

```
