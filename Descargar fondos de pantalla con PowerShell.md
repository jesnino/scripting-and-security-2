# Descargar fondos de pantalla con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/21/descargar-fondos-de-pantalla-con-powershell/
```PowerShell
(Invoke-WebRequest -Uri http://wallpaperswide.com/page/3 -UseBasicParsing).Images.src | %{Start-BitsTransfer $_}

```
