# Listar procesos de PowerShell con Node-PowerShell (Node.JS)
## JavaScript, Node.js, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/04/listar-procesos-de-powershell-con-node-powershell-nodejs/
```JavaScript
const shell = require('node-powershell');
 
let ps = new shell({
  executionPolicy: 'Bypass',
  noProfile: true
});
 
ps.addCommand('ps')
ps.invoke()
.then(output => {
  console.log(output);
})
.catch(err => {
  console.log(err);
  ps.dispose();
});

```
