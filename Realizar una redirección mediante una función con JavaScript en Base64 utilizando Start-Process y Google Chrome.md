# Realizar una redirección mediante una función con JavaScript en Base64 utilizando Start-Process y Google Chrome
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/11/06/realizar-una-redireccion-mediante-una-funcion-con-javascript-en-base64-utilizando-start-process-y-google-chrome/
```PowerShell
################################
#El código de la redirección es:
#<!doctype html><html><head><script>(function(){var a=setTimeout(function(){location.replace("https://www.jesusninoc.com")},50);window.addEventListener("beforeunload",function(){clearTimeout(a)},!0)})();</script><script>document.write('<meta name="referrer" content="'+ (navigator.userAgent.match(/(trident|msie)\/\d+/i) ? 'never' : 'no-referrer') + '">')</script><meta http-equiv="refresh" content="0;url=https://www.jesusninoc.com"></head></html>
################################
$contenido="data:text/html;base64,PCFkb2N0eXBlIGh0bWw+PGh0bWw+PGhlYWQ+PHNjcmlwdD4oZnVuY3Rpb24oKXt2YXIgYT1zZXRUaW1lb3V0KGZ1bmN0aW9uKCl7bG9jYXRpb24ucmVwbGFjZSgiaHR0cDovL3d3dy5qZXN1c25pbm9jLmNvbSIpfSw1MCk7d2luZG93LmFkZEV2ZW50TGlzdGVuZXIoImJlZm9yZXVubG9hZCIsZnVuY3Rpb24oKXtjbGVhclRpbWVvdXQoYSl9LCEwKX0pKCk7PC9zY3JpcHQ+PHNjcmlwdD5kb2N1bWVudC53cml0ZSgnPG1ldGEgbmFtZT0icmVmZXJyZXIiIGNvbnRlbnQ9IicrIChuYXZpZ2F0b3IudXNlckFnZW50Lm1hdGNoKC8odHJpZGVudHxtc2llKVwvXGQrL2kpID8gJ25ldmVyJyA6ICduby1yZWZlcnJlcicpICsgJyI+Jyk8L3NjcmlwdD48bWV0YSBodHRwLWVxdWl2PSJyZWZyZXNoIiBjb250ZW50PSIwO3VybD1odHRwOi8vd3d3Lmplc3Vzbmlub2MuY29tIj48L2hlYWQ+PC9odG1sPg=="
Start-Process chrome $contenido

```
