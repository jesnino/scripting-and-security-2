# Convertir un fichero RTF en TXT con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/06/18/convertir-un-fichero-rtf-en-txt-con-powershell/
```PowerShell
$file = "C:\Users\juan\Desktop\dplus\dplus_1.rtf"
$rtf = New-Object System.Windows.Forms.RichTextBox
$rtf.Rtf = [System.IO.File]::ReadAllText($file)
$rtf.Text | Out-File $file.replace(".rtf",".txt")

```
