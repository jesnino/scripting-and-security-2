# Abrir Notepad de forma automática con Java mediante la pulsación de teclas
## Automation, Java 
### URL: https://www.jesusninoc.com/2018/01/02/abrir-notepad-de-forma-automatica-con-java-mediante-la-pulsacion-de-teclas/
```Java
import java.awt.Robot;
import java.awt.event.KeyEvent;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		Robot r = new Robot();
		int[] executeNotepad = {KeyEvent.VK_WINDOWS,KeyEvent.VK_N,KeyEvent.VK_O,KeyEvent.VK_T,KeyEvent.VK_E,KeyEvent.VK_P,KeyEvent.VK_A,KeyEvent.VK_D,KeyEvent.VK_PERIOD,KeyEvent.VK_ENTER};
		for (int i = 0;i<executeNotepad.length ;i++ )
		{
			r.delay(500);
			r.keyPress(executeNotepad[i]);
			r.keyRelease(executeNotepad[i]);
		}
	}
}

```
