# Utilizar funciones de JavaScript en PowerShell (ScriptControl)
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/03/utilizar-funciones-de-javascript-en-powershell-scriptcontrol/
```PowerShell
#Funciona con PowerShell ISE (x86)
function Create-ScriptEngine()
{
  param([string]$language = $null, [string]$code = $null);
  if ( $language )
  {
    $sc = New-Object -ComObject ScriptControl
    $sc.Language = $language;
    if ( $code )
    {
      $sc.AddCode($code);
    }
    $sc.CodeObject;
  }
}
$jscode = @"
function multiplicar(a, b) {
 return a * b;
}
"@
$js = Create-ScriptEngine "JScript" $jscode;
$jS.multiplicar(4, 4)

```
