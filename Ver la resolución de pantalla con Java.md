# Ver la resolución de pantalla con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2017/12/26/ver-la-resolucion-de-pantalla-con-java/
```Java
import java.awt.Robot;
import java.awt.event.InputEvent;
import java.awt.*;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		GraphicsDevice gd = GraphicsEnvironment.getLocalGraphicsEnvironment().getDefaultScreenDevice();
		System.out.println("(" + gd.getDisplayMode().getWidth() +  " x " + gd.getDisplayMode().getHeight() + ")");
	}
}

```
