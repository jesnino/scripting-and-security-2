# Crear hilos desde C#
## C# 
### URL: https://www.jesusninoc.com/2017/10/03/crear-hilos-desde-c/
```C#
using System;
using System.Threading;

public class Hilo
{
    public static void Main()
    {
        // Iniciar un hilo llamando al método estático
        Thread newThread = new Thread(Hilo.DoWork);
        newThread.Start();
        Console.ReadKey();
        
        // Iniciar un hilo que llama a un método de instancia parametrizado
        Hilo w = new Hilo();
        newThread = new Thread(w.DoMoreWork);
        newThread.Start();
        Console.ReadKey();
    }

    public static void DoWork()
    {
        //Si hacemos una llamada a la Consola para que muestre un mensaje no funciona, mejor arrancar Notepad
        Console.WriteLine("Hilo con método estático");
    }

    public void DoMoreWork()
    {
        Console.WriteLine("Hilo de instancia");
    }
}

```
