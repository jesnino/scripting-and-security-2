# Extraer datos de una imagen que está subida a un servidor mediante el reconocimiento óptico de caracteres y el análisis de imágenes con Java utilizando Computer Vision API de Microsoft Azure
## Java, Recognition 
### URL: https://www.jesusninoc.com/2018/01/09/extraer-datos-de-imagenes-que-estan-subidas-a-un-servidor-mediante-el-reconocimiento-optico-de-caracteres-y-el-analisis-de-imagenes-con-java-utilizando-computer-vision-api-de-microsoft-azure/
```Java
import java.net.URI;
import org.apache.http.HttpEntity;
import org.apache.http.HttpResponse;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpPost;
import org.apache.http.entity.StringEntity;
import org.apache.http.client.utils.URIBuilder;
import org.apache.http.impl.client.DefaultHttpClient;
import org.apache.http.util.EntityUtils;
import org.json.JSONObject;

public class Main
{
    public static final String subscriptionKey = "Clave del API";

    public static final String uriBase = "https://westcentralus.api.cognitive.microsoft.com/vision/v1.0/analyze";


    public static void main(String[] args)
    {
        HttpClient httpclient = new DefaultHttpClient();

        try
        {
            URIBuilder builder = new URIBuilder(uriBase);

            // Valores que se añaden a la URI
            builder.setParameter("visualFeatures", "Categories,Description,Color");
            builder.setParameter("language", "en");

            // Preparar la URI para la llamada REST API
            URI uri = builder.build();
            HttpPost request = new HttpPost(uri);

            // Componer las Cabeceras
            request.setHeader("Content-Type", "application/json");
            request.setHeader("Ocp-Apim-Subscription-Key", subscriptionKey);

            // Componer el Body
            StringEntity reqEntity = new StringEntity("{\"url\":\"http://www.abc.es/media/motor/2017/09/26/accidente-puigdemont-kZiE--510x286@abc.JPG\"}");
            request.setEntity(reqEntity);

            // Ejecutar la peticióni REST API con los valores
            HttpResponse response = httpclient.execute(request);
            HttpEntity entity = response.getEntity();

            if (entity != null)
            {
                // Obtener resultado JSON
                String jsonString = EntityUtils.toString(entity);
                JSONObject json = new JSONObject(jsonString);
                // Obtener la descripción de la imagen
                System.out.println(json.get("description"));
            }
        }
        catch (Exception e)
        {
            // Mostrar mensajes de error si salta excepción
            System.out.println(e.getMessage());
        }
    }
}

```
