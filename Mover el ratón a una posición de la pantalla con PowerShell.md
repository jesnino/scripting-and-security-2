# Mover el ratón a una posición de la pantalla con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/01/mover-el-raton-a-una-posicion-de-la-pantalla-con-powershell/
```PowerShell
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(100,100)

```
