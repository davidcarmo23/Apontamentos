# Aula 1
# Aula 2
# Aula 3
# Aula 4
# Aula 5
# Aula 6

## Armazenamento
**Não existe solução para dados perdidos**
 Dados são o combústivel das organizações modernas. É inevitável em algum ponto perder dados.

**Razões para Perda de Dados**
- *Erros Humanos*
	- Apagar ficheiros
	- Sobreescrever ficheiros
- *Erros de Software*
	- Apagar ficheiros
	- Ficheiros Corrompidos
	- Sobreescrever ficheiros
	- Virús , trojans, ransomware....

**3 Formas básicas de armazenamento em rede**

Aparelhos dedicados para o armazenamento de um servidor.
- **NAS** (Network Attached Storage )
- **DAS** (Direct Attached Storage) 
- **SAN** (Storage Area Network)

**Exemplificação**

![[Pasted image 20220427190637.png]]


## **SAN**
 Ao longo dos anos verificamos um **aumento da necessidade de uma maior velocidade para armazenamento e rede** .

### **NAS**
 
## Protocolos para partilhar volumes
### **O que é um volume ?**
Um disco tem partições , cada partição é um volume esta divisão pode ser mais complexa e um volume pode extender-se por vários discos. 

Em **Windows** estes discos podem ser chamados por uma Letra e dois pontos (EX: C:).
Em máquinas **X** os volumes são montados numa diretoria dentro de outra com o nome de **Volumes**.

No entanto isto não assegura **Redundância de Dados** e sem isto estamos sempre em risco.

### **RAID**
Tecnologia de virtualização de armazenamento, combine vários discos fisícos em uma ou mais unidade lógica para assegurar **Redundância de Dados**.

Existem várias variações de **Raid**:
- *RAID 0*
	- Volumes "Stripped"
	- Distribui os dados pelos discos
	- Aumenta a velocidade de acesso
- *RAID 1*
	- Copia os dados entre os discos
	- Assegura redundância
- *RAID 2*. 3*, 4, 5, 6*
	- Dados "Stripped" (bit, Byte, blocos, distribuído por blocos, distribuído duplamente por blocos ) + correção de erros
- *RAID 10*
	- RAID 0 + RAID 1

 *Não é comum ser utilizado* *

**RAID implementado por Software ou Hardware**
- **OS** consegue lidar com a redundância de dados e o "Stripping"
- **HW/ Controladores HD** dedicados para fazer o trabalho pelo OS

### **Coisas que o RAID não faz**
- Não equaciona 100% do uptime
- Não substitui cópias de segurança (**Backups**)
- Não protege contra **corrupção, erros humanos ou problemas de segurança**
- Não permite necessariamente aumentar dinamicamente o **tamanho do array**
- Nem sempre é a melhor opção para **virtualização** e **high-availability failover**

**Hot Swap** - Substituir o disco sem desligar o sistema.

## Filesystems


