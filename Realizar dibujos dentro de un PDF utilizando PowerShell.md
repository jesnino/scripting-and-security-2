# Realizar dibujos dentro de un PDF utilizando PowerShell
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2017/08/20/realizar-dibujos-dentro-de-un-pdf-utilizando-powershell/
```PowerShell
#Descargar https://sourceforge.net/projects/itextsharp/

[System.Reflection.Assembly]::LoadFrom("E:\programas\itextsharp-dll-core\itextsharp.dll")

$doc=New-Object itextsharp.text.document
$stream=[IO.File]::OpenWrite("output.pdf")
$writer=[itextsharp.text.pdf.PdfWriter]::GetInstance($doc, $stream)

$doc.Open()

$dc = $writer.DirectContent

#Crear dos líneas en la parte inferior del documento PDF
$dc.MoveTo(0, 100)
$dc.LineTo($doc.PageSize.Width, 100)
$dc.Stroke()
$dc.MoveTo(0, 200)
$dc.LineTo($doc.PageSize.Width, 200)
$dc.Stroke()

#Dibujar un cuadrado
$dc.MoveTo(100, 700)
$dc.LineTo(200, 700)
$dc.LineTo(200, 600)
$dc.LineTo(100, 600)
$dc.ClosePath()
$dc.Stroke()

#Dibujar un cuadrado
$dc.Rectangle($doc.PageSize.Width-200, 600, 100, 100);
$dc.Stroke();

#Dibujar un círculo de color rojo
$dc.SetCMYKColorStroke(255, 255, 0, 0);
$dc.SetCMYKColorFill(0, 255, 255, 0);
$dc.SetLineWidth(2);
$dc.Circle(120, 250, 50);
$dc.Fill();

$doc.Close()
$stream.Close()

.\output.pdf

```
