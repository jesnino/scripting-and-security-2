# Compiling a C Program on the Bash in PowerShell
## C, PowerShell 
### URL: https://www.jesusninoc.com/2018/07/03/compiling-a-c-program-on-the-bash-in-powershell/
```C
#include <stdio.h>
int main()
{
        printf("Hola Mundo.\n");
        return 0;
}

```
```PowerShell
wsl cat hola.c
wsl gcc hola.c
wsl ./a.out

```
