# Serializar y deserializar un objeto almacenado en un fichero en Java
## Java 
### URL: https://www.jesusninoc.com/2018/01/07/serializar-y-deserializar-un-objeto-almacenado-en-un-fichero-en-java/
```Java
public class Persona implements java.io.Serializable {
    String nombre;

    public Persona(String parametro)
    {
        nombre = parametro;
    }
    @Override
    public String toString() {
        return "Nombre: " + nombre;
    }
}

```
```Java
import java.io.*;

public class Serializar {
    public static void main(String[] args) {
        try {
            FileOutputStream fos = new FileOutputStream("fichero.txt");
            ObjectOutputStream sos = new ObjectOutputStream(fos);
            sos.writeObject(new Persona("Carlos"));
            sos.close();
        }
        catch (FileNotFoundException ex) {
            ex.printStackTrace();
        }
        catch (IOException ex) {
            ex.printStackTrace();
        }
    }
}

```
```Java
import java.io.*;
import java.util.Date;

public class Deserializar {
    public static void main(String[] args) {
        try {
            FileInputStream fis = new FileInputStream("fichero.txt");
            ObjectInputStream sis = new ObjectInputStream(fis);
            System.out.println((Persona)sis.readObject());
            sis.close();
        }
        catch (FileNotFoundException ex) {
            ex.printStackTrace();
        }
        catch (IOException ex) {
            ex.printStackTrace();
        }
        catch(ClassNotFoundException ex) {
            ex.printStackTrace();
        }
    }
}

```
