# Mostrar enlaces de una web usando JavaScript
## JavaScript 
### URL: https://www.jesusninoc.com/2017/10/12/mostrar-enlaces-de-una-web-usando-javascript/
```JavaScript
var links = document.links;
​
for(var i=0;i<links.length;i++)
{
    console.log("Enlace#"+(i+1)+":"+links[i].href);
}

```
