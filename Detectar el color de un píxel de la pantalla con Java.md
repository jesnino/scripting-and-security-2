# Detectar el color de un píxel de la pantalla con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2018/01/10/detectar-el-color-de-un-pixel-de-la-pantalla-con-java/
```Java
import java.awt.Color;
import java.awt.Robot;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		Color color = (new Robot()).getPixelColor(10, 10);
		System.out.println("Red   = " + color.getRed());
		System.out.println("Green = " + color.getGreen());
		System.out.println("Blue  = " + color.getBlue());
	}
}

```
