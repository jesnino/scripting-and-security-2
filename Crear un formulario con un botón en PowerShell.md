# Crear un formulario con un botón en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/25/crear-un-formulario-con-un-boton-en-powershell/
```PowerShell
using assembly System.Windows.Forms
using namespace System.Windows.Forms
$form = [Form] @{
 Text = 'Mi formulario'
}
$button = [Button] @{
 Text = 'Pulsar'
 Dock = 'Fill'
}
$button.add_Click{
 $form.Close()
}
$form.Controls.Add($button)
$form.ShowDialog()

```
