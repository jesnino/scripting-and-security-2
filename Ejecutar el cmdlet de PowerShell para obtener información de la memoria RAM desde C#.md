# Ejecutar el cmdlet de PowerShell para obtener información de la memoria RAM desde C#
## C#, Hardware, Memory, PowerShell 
### URL: https://www.jesusninoc.com/2017/10/13/ejecutar-el-cmdlet-de-powershell-para-obtener-informacion-de-la-memoria-ram-desde-c/
```C#
using System;
using System.Management.Automation;  // Windows PowerShell namespace.

namespace HostPS1
{
    class HostPS1
    {
        static void Main(string[] args)
        {

            // Call the PowerShell.Create() method to create an 
            // empty pipeline.
            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Get-WmiObject");
            ps.AddArgument("win32_physicalmemory");
            ps.AddCommand("sort-object");
            ps.AddArgument("Manufacturer");

            // Call the PowerShell.Invoke() method to run the 
            // commands of the pipeline in the default runspace.
            foreach (PSObject result in ps.Invoke())
            {
                Console.WriteLine(result.Members["Manufacturer"].Value);
            } // End foreach.
        } // End Main.
    } // End HostPs1.
}

```
