# Mover el ratón con duración a varias posiciones de la pantalla con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2017/12/24/mover-el-raton-con-duracion-a-varias-posiciones-de-la-pantalla-con-java/
```Java
import java.awt.Robot;
import java.awt.event.InputEvent;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		Robot r = new Robot();
		r.mouseMove(10,10);
		r.delay(500);
		r.mouseMove(20,10);
		r.delay(500);
		r.mouseMove(30,10);
		r.delay(500);
	}
}

```
