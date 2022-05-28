# Sistemas Distribuidos

## Aula 3
**Thread** -> Sequência de execução independente
As várias threads de um processo partilham o mesmo espaço de endereçamento que o processo (pai) que lhe deu origem
![[Pasted image 20220528192356.png]]

**Criação de Threads em JAVA**
![[Pasted image 20220528192453.png]]
![[Pasted image 20220528192509.png]]

**Aceder a um Objeto Partilhado**
![[Pasted image 20220528192559.png]]

**Se a classe for subclasse de outra classe**
![[Pasted image 20220528192651.png]]

### Diagramas de Estados Possiveis para uma Thread
![[Pasted image 20220528192729.png]]

**Sincronização de Threads** -> Mecanismo baseado no conceito de monitor

![[Pasted image 20220528192807.png]]

Após calcular a referência para o objecto, mas antes de executar o corpo de instruções:

- A thread adquire o lock associado ao objeto (caso este não pertença já a alguma outra thread)
	- Executa o corpo de instruções
- Após Executar o corpo de instruções
	- Liberta o lock

**Notas**

