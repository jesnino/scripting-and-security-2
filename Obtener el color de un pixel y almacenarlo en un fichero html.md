# Obtener el color de un pixel y almacenarlo en un fichero html
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/16/obtener-el-color-de-un-pixel-y-almacenarlo-en-un-fichero-html/
```PowerShell
$GDI = Add-Type -MemberDefinition @'
[DllImport("user32.dll")]
static extern IntPtr GetDC(IntPtr hwnd);

[DllImport("user32.dll")]
static extern Int32 ReleaseDC(IntPtr hwnd, IntPtr hdc);

[DllImport("gdi32.dll")]
static extern uint GetPixel(IntPtr hdc,int nXPos,int nYPos);

static public int GetPixelColor(int x, int y)
{
IntPtr hdc = GetDC(IntPtr.Zero);
uint pixel = GetPixel(hdc, x, y);
ReleaseDC(IntPtr.Zero,hdc);

return (int)pixel;
}
'@ -Name GDI -PassThru

for ()
{
Start-Sleep -m 1000
$dX = ([System.Windows.Forms.Cursor]::Position.X) #X coordinates
$dY = ([System.Windows.Forms.Cursor]::Position.Y) #Y coordinates
Write-Host $dX,$dY #print coordinates

$PixelColorRef = $GDI::GetPixelColor($dX,$dY)
[System.Drawing.Color]::FromArgb($PixelColorRef)
'<font size=''2'' color=''' + [System.Drawing.Color]::FromArgb($PixelColorRef).name + '''>█</font>' | Out-File d:\colores.html -Append
}

```
