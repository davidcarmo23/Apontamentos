## Base de dados 
Coleção partilhada de dados (ficheiros) logicamente relacionados concebida de forma a satisfazer as necessidades de informação duma organização
## DBMS
Colecção de programas que permite ao utilizador definir, criar, aceder, manipular e fazer a manutenção os dados existentes numa DB.
![[Pasted image 20221110190658.png]]

## Projeto (Desenho) de bases de dados
começa por uma descrição começa por uma descrição abstrata e, por isso, geral dos requisitos de informação duma organização: abstrata e, por isso, geral dos requisitos de informação duma organização: 
- Entidades 
- Atributos 
- Relações
## Níveis de abstração de dados (ANSI)

![[Pasted image 20221110191029.png]]
**Nível externo  (utilizador)**: descrição  personalizada e parcial dos dados.
Cada **perspetiva (view) externa** inclui as entidades , atributos e relações que são relevantes  para o utilizador ou departamento em causa
**Nível conceptual (DBA)**: descrição comunitária/total dos dados. Descreve *QUE* dados e suas relações estão armazenados na BD.
**Nível interno (sistema)**: Representação física da BD. Descrição Descrição de *COMO* os dados estão armazenados (estruturas de dados e ficheiros usados ao mais baixo-nível).

## Esquemas e Instâncias
![[Pasted image 20221110191312.png]]

## Independência lógica dos dados
invariância dos sub-esquemas externos a quaisquer alterações no esquema conceptual.
## Independência física dos dados
invariância do esquema conceptual externos a quaisquer alterações no esquema interno

## DDL Data Definition Language
![[Pasted image 20221110191720.png]]

## DML Data Manipulation Language
![[Pasted image 20221110191747.png]]

## SQL Structured Query Language
![[Pasted image 20221110191810.png]]

## Modelos de Dados
![[Pasted image 20221110191827.png]]

## Funções/Serviços de um DBMS 
![[Pasted image 20221110191853.png]]

## Componentes de um DBMS
![[Pasted image 20221110191915.png]]

## Topologias de Rede para DBMS
![[Pasted image 20221110191943.png]]

### Teleprocessamento
![[Pasted image 20221110192022.png]]

### Ficheiro Servidor
![[Pasted image 20221110192049.png]]

### Cliente Servidor
![[Pasted image 20221110192103.png]]