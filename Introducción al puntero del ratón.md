# Introducción al puntero del ratón
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/10/introduccion-al-puntero-del-raton/
```PowerShell
#Obtiene o establece un objeto cursor que representa el cursor del mouse

#Obtener la posición del ratón
[System.Windows.Forms.Cursor]::Position

#Obtener la posición X del ratón
([System.Windows.Forms.Cursor]::Position).X

#Obtener la posición Y del ratón
([System.Windows.Forms.Cursor]::Position).Y

#Mover el cursor del ratón a la posición 100,100
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(100,100)

```
