# Realizar una captura de pantalla de toda la pantalla con Java
## Automation, Java 
### URL: https://www.jesusninoc.com/2018/01/19/realizar-una-captura-de-pantalla-de-toda-la-pantalla-con-java/
```Java
import java.awt.Rectangle;
import java.awt.Robot;
import java.awt.image.BufferedImage;
import java.io.File;
import java.awt.Toolkit;
import javax.imageio.ImageIO;

public class Robots
{
	public static void main(String[] args) throws Exception
	{
		BufferedImage bufferedImage = (new Robot()).createScreenCapture(new Rectangle(Toolkit.getDefaultToolkit().getScreenSize()));
		ImageIO.write(bufferedImage,"PNG", new File("imagen.PNG"));
	}
}

```
