# Mover el ratón a una posición con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2017/12/18/mover-el-raton-a-una-posicion-con-java/
```Java
import java.awt.Robot;
import java.awt.event.InputEvent;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		Robot r = new Robot();
		r.mouseMove(100,100);
	}
}

```
