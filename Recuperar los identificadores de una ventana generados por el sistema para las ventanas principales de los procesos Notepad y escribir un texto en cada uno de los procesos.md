# Recuperar los identificadores de una ventana generados por el sistema para las ventanas principales de los procesos Notepad y escribir un texto en cada uno de los procesos
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/18/recuperar-los-identificadores-de-una-ventana-generados-por-el-sistema-para-las-ventanas-principales-de-los-procesos-notepad-y-escribir-un-texto-en-cada-uno-de-los-procesos/
```PowerShell
#La función FindWindowEx
#Recupera un identificador a una ventana cuyo nombre de clase y nombre de la ventana que coincida con las cadenas especificadas. La función busca en ventanas secundarias, comenzando por la raíz de la ventana secundaria especificada. Esta función no realiza una búsqueda entre mayúsculas y minúsculas.
#La función SendMessage
#Envía el mensaje especificado a una ventana o ventanas. La función SendMessage llama al procedimiento de ventana de la ventana especificada y no vuelve hasta que el procedimiento de ventana ha procesado el mensaje.

$codigo='
[DllImport("user32.dll", EntryPoint = "FindWindowEx")]public static extern IntPtr FindWindowEx(IntPtr hwndParent, IntPtr hwndChildAfter, string lpszClass, string lpszWindow);
[DllImport("User32.dll")]public static extern int SendMessage(IntPtr hWnd, int uMsg, int wParam, string lParam);
'

$acciones=Add-Type -MemberDefinition $codigo -Name TextoNotepad -PassThru

#Para cada proceso Notepad abierto, escribir un texto
(Get-Process Notepad | Select-Object Name,MainWindowHandle).MainWindowHandle | %{
$acciones::SendMessage([IntPtr]$acciones::FindWindowEx($_, [IntPtr]::Zero, "Edit", $null), 0x000C, 0, "Texto")
}

```
