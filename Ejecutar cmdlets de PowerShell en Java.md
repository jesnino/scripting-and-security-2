# Ejecutar cmdlets de PowerShell en Java
## Java, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/22/ejecutar-cmdlets-de-powershell-en-java/
```Java
import java.io.IOException;
import java.util.concurrent.TimeUnit;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ProcesoPowerShell
{
	public static void main(String[] args) throws InterruptedException
	{		
		Runtime runtime = Runtime.getRuntime();
		try
		{
			Process process = runtime.exec("powershell.exe  $PSVersionTable.PSVersion");
			
			process.getOutputStream().close();
			String line;
			BufferedReader stdout = new BufferedReader(new InputStreamReader(process.getInputStream()));
			while ((line = stdout.readLine()) != null){
				System.out.println(line);
			}

			TimeUnit.SECONDS.sleep(10);
		}
		catch(IOException ex){
			System.err.println("Error");
			System.exit(-1);
		}
	}
}

```
