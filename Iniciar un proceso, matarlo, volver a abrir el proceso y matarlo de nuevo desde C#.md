# Iniciar un proceso, matarlo, volver a abrir el proceso y matarlo de nuevo desde C#
## C#, Processes 
### URL: https://www.jesusninoc.com/2017/10/10/iniciar-un-proceso-matarlo-volver-a-abrir-el-proceso-y-matarlo-de-nuevo-desde-c/
```PowerShell
using System;
using System.Diagnostics;
using System.Threading;

public class Proceso
{
    public static void Main()
    {

        Process myProcess;
        myProcess = Process.Start(@"C:\Windows\System32\Notepad.exe");
        Thread.Sleep(2000);
        myProcess.Kill();

        myProcess.Start();
        Thread.Sleep(2000);
        myProcess.Kill();
        
        // Free resources associated with process.
        myProcess.Close();
    }
}

```
