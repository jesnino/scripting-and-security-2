# Convertir HTML a epub mediante WSL desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/28/convertir-html-a-epub-mediante-wsl-desde-powershell/
```PowerShell
wsl wget https://www.jesusninoc.com
bash -c 'pandoc -f html -t epub3 -o output.epub index.html'

```
