# Mostrar los eventos (clic izquierdo, derecho o centro) y las coordenadas del ratón en PowerShell
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/12/14/mostrar-los-eventos-clic-izquierdo-derecho-o-centro-y-las-coordenadas-del-raton-en-powershell/
```PowerShell
while(1)
{
[System.Windows.Forms.UserControl]::MouseButtons
[System.Windows.Forms.Cursor]::Position 
}

```
