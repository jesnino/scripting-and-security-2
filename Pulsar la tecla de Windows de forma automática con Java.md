# Pulsar la tecla de Windows de forma automática con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2017/12/30/pulsar-la-tecla-de-windows-de-forma-automatica-con-java/
```Java
import java.awt.Robot;
import java.awt.event.KeyEvent;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		Robot r = new Robot();
		r.keyPress(KeyEvent.VK_WINDOWS);
		r.keyRelease(KeyEvent.VK_WINDOWS);
	}
}

```
