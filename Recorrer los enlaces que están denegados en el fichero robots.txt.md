# Recorrer los enlaces que están denegados en el fichero robots.txt
## PowerShell, Web Service 
### URL: https://www.jesusninoc.com/2016/10/19/recorrer-los-enlaces-que-estan-denegados-en-el-fichero-robots-txt/
```PowerShell
$url='https://jesusninoc.com/'
(Invoke-WebRequest $url"robots.txt").content -split "`n" | %{
    if($_ -match "/")
    {
        (Invoke-WebRequest ($url+$_).Replace("Disallow: /",""))
    }
}

```
