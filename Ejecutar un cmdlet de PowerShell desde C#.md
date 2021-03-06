# Ejecutar un cmdlet de PowerShell desde C#
## C#, PowerShell 
### URL: https://www.jesusninoc.com/2017/10/20/ejecutar-un-cmdlet-de-powershell-desde-c-2/
```C#
using System;
using System.Management.Automation;  // Windows PowerShell namespace.

namespace PowerSh
{
    class PowerSh
    {
        static void Main(string[] args)
        {

            //Create a PowerShell object.
            PowerShell ps = PowerShell.Create();
            //Add the command that you want to execute.
            ps.AddCommand("Get-Process");
            //Add the command that you want to execute.
            ps.AddCommand("out-file");
            //Add the argument
            ps.AddArgument("out.txt");
            //Invoke the command.
            ps.Invoke();

        } // End Main.
    } // End HostPs1.
}

```
# Ejecutar un cmdlet de PowerShell desde C#
## C#, PowerShell 
### URL: https://www.jesusninoc.com/2017/10/09/ejecutar-un-cmdlet-de-powershell-desde-c/
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

            // Call the PowerShell.AddCommand(string) method, add 
            // the Get-Process cmdlet to the pipeline. Do 
            // not include spaces before or after the cmdlet name 
            // because that will cause the command to fail.
            ps.AddCommand("Get-Process");

            Console.WriteLine("Process                 Id");
            Console.WriteLine("----------------------------");


            // Call the PowerShell.Invoke() method to run the 
            // commands of the pipeline in the default runspace.
            foreach (PSObject result in ps.Invoke())
            {
                Console.WriteLine("{0,-24}{1}",
                        result.Members["ProcessName"].Value,
                        result.Members["Id"].Value);
            } // End foreach.
        } // End Main.
    } // End HostPs1.
}

```
