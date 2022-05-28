# Sistemas Distribuidos

## Aula 2

### O que é a computação Distribuida?
A computação é dividida em várias unidades que executam concorrentemente  em diferentes elementos de computação. Podem ser diferentes processadores em diferentes máquinas, diferentes processadores na mesma máquina ou diferentes cores no mesmo processador.

Um **sistema distribuido** é resultado da interação de vários componentes que atravessam toda a pilha de computação desde o hardware até ao software.

**Hardware** -> Computadores mais infra-estrutura de rede
É gerido pelo SO que forneçe os serviços para:
![[Pasted image 20220528175705.png]]

Ao nivel do **sistema operativo,** a comunicação entre  processos é implementada usando protocolos como:
![[Pasted image 20220528175747.png]]


A **comunicação entre processo IPC** é usada tanto para transferir dados entre os processo tal como para coordenar a sua atividade.

**Modelos de IPC mais importantes**:
- Memória Partilhada
- Comunicação por mensagens

### Sistema de Memória Partilhada

![[Pasted image 20220528180208.png]]

### Sistema de Memória Distribuida
![[Pasted image 20220528180234.png]]

As várias **formas de comunicação por mensagens** distinguem-se por dois aspetos:

- **Tipo de Sincronização**
	- ![[Pasted image 20220528180507.png]]
- **Forma como são especificados os vários intervenientes no processo**
	- ![[Pasted image 20220528180549.png]]


**Três tipos de sincronização**

- Comunicação síncrona
	- ![[Pasted image 20220528180818.png]]
	- **Conceito de mais baixo nível (mais eficiente)**
- Comunicação assíncrona
	- ![[Pasted image 20220528180913.png]]
	- **Permite um maior grau de concorrência**
	- Exige que o sistema de execução faça a gestão e o **armazenamento das mensagens**

### Invocação Remota de Procedimentos
- **Remote Procedure Calling**
	- ![[Pasted image 20220528181029.png]]
	- ![[Pasted image 20220528181036.png]]
	- ![[Pasted image 20220528181043.png]]

- **Vari**