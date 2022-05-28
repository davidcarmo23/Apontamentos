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

- **Variante do RPC**
	- ![[Pasted image 20220528181211.png]]
	- ![[Pasted image 20220528181217.png]]
	- ![[Pasted image 20220528181234.png]]
### Identificação dos processos

- **Sistema em que todos os processos têm um nome único**
	- ![[Pasted image 20220528181517.png]]
- Quando não é apropriado um sistema de nomes únicos para todos os processos, definem-se entidades intermédias
	- ![[Pasted image 20220528181653.png]]

### Formas de Criação de processos
**Definição estática** -> 
![[Pasted image 20220528181739.png]]

**Definição dinâmica** ->
![[Pasted image 20220528181812.png]]

**Socket** -> interface de um canal de comunicação entre dois processos. Um par de processos comunica através de um par de sockets

**Paradigma de Comunicação**
![[Pasted image 20220528181945.png]]

### Endereço de um Socket
É especificado por 
- **Endereço Internet** -> IP da máquina onde está o processo com que queremos comunicar
- **Nº de um porto** -> um porto é representado por um inteiro >1024 que identifica os vários serviços em execução numa mesma máquina, 0-1023 reservados a utilizadores com privilégios root ou superuser

**A Classe Socket**

- Permite criar sockets que comunicam através do protocolo TCP usando uma stream de bytes.
- Um dos sockets (servidor) aguarda por um pedido de ligação enquanto o outro (cliente) solicita a ligação.
- Após ser estabelecida a ligação, estes podem ser usados para transmitir dados nos **dois sentidos**

**Criar um Socket**

![[Pasted image 20220528183513.png]]

**Criar um Socket se for um Servidor**

![[Pasted image 20220528183722.png]]

Ex Percorrer todos os portos de uma máquina remota

![[Pasted image 20220528183945.png]]

**Criar uma output stream (Cliente)**
![[Pasted image 20220528184256.png]]

**Criar uma output stream (Servidor)**

![[Pasted image 20220528184334.png]]

**Criar uma input stream (Servidor)**
![[Pasted image 20220528184431.png]]

**Criar uma input stream (Servidor)**
![[Pasted image 20220528184440.png]]

**Fechar um socket**
![[Pasted image 20220528184502.png]]

### **Os Sistemas de Objetos Distribuidos implementam o modelo de objetos locais usando RPC**

![[Pasted image 20220528185819.png]]
![[Pasted image 20220528185925.png]]

### Web Services

![[Pasted image 20220528190001.png]]

