# Hacer clic en una posición de la pantalla con Python
## Automation, Python 
### URL: https://www.jesusninoc.com/2017/11/21/hacer-clic-en-una-posicion-de-la-pantalla-con-python/
```Python
# Es necesario instalar pywin32 https://sourceforge.net/projects/pywin32/files/
import win32api, win32con
def clic(x,y):
    win32api.SetCursorPos((x,y))
    win32api.mouse_event(win32con.MOUSEEVENTF_LEFTDOWN,x,y,0,0)
    win32api.mouse_event(win32con.MOUSEEVENTF_LEFTUP,x,y,0,0)
clic(10,10)

```
