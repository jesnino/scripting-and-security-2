# Utilizar la entrada y salida estándar
## Java 
### URL: https://www.jesusninoc.com/2018/01/03/utilizar-la-entrada-y-salida-estandar/
```Java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class EntradaSalida
{
	public static void main(String[] args)
	{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		System.out.println("Escribir una palabra: ");
		try
		{
			String aux = br.readLine();
			System.out.println("La palabra es: " + aux.toUpperCase());
		}
		catch(IOException ex)
		{
			ex.printStackTrace();
		}
	}
}

```
