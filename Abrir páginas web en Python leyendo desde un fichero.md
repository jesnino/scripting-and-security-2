# Abrir páginas web en Python leyendo desde un fichero
## Automation, Python, Web 
### URL: https://www.jesusninoc.com/2017/12/25/abrir-paginas-web-en-python-leyendo-desde-un-fichero/
```Python
import webbrowser
infile = open('urls.txt', 'r')
for line in infile:
    print(line)
    webbrowser.open(line)    
infile.close()

```
