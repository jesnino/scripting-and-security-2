# Convert una imagen JPG a HTML
## Automation, Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/08/convert-una-imagen-jpg-a-html/
```PowerShell
#IMPORTANT
#Path file
#Character █
#Quotes

$Cave = [System.Drawing.Bitmap]::FromFile( '.\juan2.jpg' )
$i=0

for ($x = 0;$x -lt $Cave.Height;$x+=1)
{
    for ($y = 0;$y -lt $Cave.Width;$y+=1)
    {
        if ($i -lt $Cave.Width -1)
        {
            $com ="<font size=""2"" color=""" + ($Cave.GetPixel($y,$x).name).substring(2,6) + """>█</font>"
            $i=$i+1
        }
        else
        {
            $com = "<br>"
            $i=0
            $a=0
        }
        $com | Out-File traducir2.html -Append
    }
}

```
