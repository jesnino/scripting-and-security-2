# Obtener la posición del ratón en la pantalla con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2017/12/28/obtener-la-posicion-del-raton-en-la-pantalla-con-java/
```Java
import java.awt.MouseInfo;
import java.awt.Robot;
import java.awt.event.InputEvent;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		System.out.println("(" + MouseInfo.getPointerInfo().getLocation().x +  ", " + MouseInfo.getPointerInfo().getLocation().y + ")");
	}
}

```
