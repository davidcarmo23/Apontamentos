# Lab 3
## Tarefa 1
**gcc nomeprograma.c -o programanome**
**./programanome**

```C
#include<stdio.h> 
#include<math.h> 
int main(){ 
	unsigned int ikey = 123456789; 
	srand(ikey); 
	int i; 
	for( i = 0; i < 1000; i++) 
		printf("%u\n", (unsigned int) rand()); }
```

### Questão 1
32
### Questão 2
Sim, é, porque a sequência depende apenas do valor inicial (seed) que, neste caso, é igual nos dois casos.
## Tarefa 2
```c
#include <stdio.h> 
#include<math.h> 
#include<stdlib.h> 
void encrypt (char * in, char * out, int ikey) { 
	FILE _fIN = fopen(in, "r"); 
	FILE_fOUT = fopen(out, "w"); 
	int b; 
	while (!feof(fIN)){ 
		b = fgetc(fIN); 
		b = b ^ rand(); 
		printf("%x\n", b); 
		fputc(b, fOUT); 
		} 
	} 
	int main(){ 
	unsigned int ikey = 123456789;  
	encrypt("plaintext.txt", "cypher.txt", ikey);
	}
```
## Tarefa 3
