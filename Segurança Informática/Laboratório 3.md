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
## Tarefa 2/Tarefa 3
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
## Tarefa 4
Basta trocar a ordem dos ficheiros

### Questão 5
Hummm, o facto do Prof. estar a perguntar deixame desconfiado(a)...

# Tarefa 5

### Questão 6
Não... de maneira nenhuma. Que estranho!?
### Questão 7
Sim, neste caso poder-se-ia dizer isso.
### Questão 8
Cifra de chave simétrica por blocos.

## Tarefa 7
## Tarefa 8

### Questão 9
Sim, noto algo até meio (vá) assustador!
### Questão 10
Sim, pelos vistos sim.
### Questão 11
0
### Questão 12
Sim, sem problema.