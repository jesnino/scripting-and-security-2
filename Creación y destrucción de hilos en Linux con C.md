# Creación y destrucción de hilos en Linux con C
## Bash, C 
### URL: https://www.jesusninoc.com/2018/06/20/creacion-y-destruccion-de-hilos-en-linux-con-c/
```C
#include <stdlib.h>
#include <pthread.h>
#include <stdio.h>
#define NUM_HILOS 5

void *DiHola(void *hiloid)
{
	long tid;
	tid = (long)hiloid;
	printf("Soy el hilo #%ld!\n", tid);
	pthread_exit(NULL);
}

int main (int argc, char *argv[])
{
	pthread_t hilos[NUM_HILOS];
	int rc;
	long t;
	for(t=0; t<NUM_HILOS; t++){
		printf("Soy la rutina principal y mi identificador es %ld\n", t);
		rc = pthread_create(&hilos[t], NULL, DiHola, (void *)t);
		if (rc){
			printf("ERROR: El código es %d\n", rc);
			exit(-1);
		}
	}
	pthread_exit(NULL);
}

```
```Shell
gcc -pthread -o hilos hilo.c

```
