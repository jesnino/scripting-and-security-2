# Crear un fichero PDF con el contenido de la tabla posts de WordPress con PowerShell
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/08/crear-un-fichero-pdf-con-el-contenido-de-la-tabla-posts-de-wordpress-con-powershell/
```PowerShell
#Conexión a MySQL
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + ";database="+"jesusninoc"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

#Consulta para obtener título y contenido a la base de datos de Wordpress
$Query='select post_title, post_content from wp_posts where id=5'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0].post_content

#Crear el PDF con el título y el contenido
#Descargar https://sourceforge.net/projects/itextsharp/
[System.Reflection.Assembly]::LoadFrom("E:\programas\itextsharp-dll-core\itextsharp.dll")

#Crear el documento PDF
$document=New-Object itextsharp.text.document
$stream=[IO.File]::OpenWrite("output.pdf")
[itextsharp.text.pdf.PdfWriter]::GetInstance($document, $stream)

#Para cada elemento de la tabla añadir al documento PDF
$document.Open()
$DataSet.Tables[0] | %{
$title=New-Object itextsharp.text.Paragraph($_.post_title)
$document.Add($title)
$content=New-Object itextsharp.text.Paragraph($_.post_content)
$document.Add($content)
}

#Cerrar documento PDF
$document.Close()
$stream.Close()

#Cerrar conexión a MySQL
$Connection.Close()

#Abrir el PDF creado
Start-Process .\output.pdf

```
