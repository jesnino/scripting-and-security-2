# Enviar una imagen entre un cliente y un servidor con Java (Sockets TCP)
## Java, Network 
### URL: https://www.jesusninoc.com/2018/01/29/enviar-una-imagen-entre-un-cliente-y-un-servidor-con-java-sockets-tcp/
```Java
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.*;
import java.net.*;
import java.nio.ByteBuffer;

public class Server
{
    public static void main(String[] args)
    {
        int port=2050;
        try
        {
            ServerSocket serverSocket = new ServerSocket(port);

            Socket clientSocket = serverSocket.accept();

            InputStream inputStream = clientSocket.getInputStream();

            System.out.println(inputStream);

            byte[] imageAr = new byte[62100];
            inputStream.read(imageAr);

                BufferedImage image = ImageIO.read(new ByteArrayInputStream(imageAr));

            System.out.println("Received " + image.getHeight() + "x" + image.getWidth() + ": " + System.currentTimeMillis());
            ImageIO.write(image, "jpg", new File("C:\\Users\\juan\\Desktop\\recono\\coche2.png"));

            inputStream.close();
            clientSocket.close();
            serverSocket.close();
        }
        catch (UnknownHostException e){
            System.out.println(e);
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}

```
```Java
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.*;
import java.net.*;
import java.nio.ByteBuffer;

public class Client
{
    public static void main(String[] args)
    {
        int port=2050;
        try
        {
            Socket clientSocket = new Socket("localhost",port);

            OutputStream outputStream = clientSocket.getOutputStream();

            ByteArrayOutputStream byteArrayOutputStream = new ByteArrayOutputStream();

            BufferedImage image = ImageIO.read(new File("C:\\Users\\juan\\Desktop\\recono\\coche.png"));
            ImageIO.write(image, "jpg", byteArrayOutputStream);

            byte[] size = ByteBuffer.allocate(4).putInt(byteArrayOutputStream.size()).array();
            System.out.println(byteArrayOutputStream.size());
            outputStream.write(byteArrayOutputStream.toByteArray());
            Thread.sleep(2000);

            outputStream.close();
            clientSocket.close();
        }
        catch (UnknownHostException e){
            System.out.println(e);
        }
        catch (IOException e) {
            System.out.println(e);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}

```
