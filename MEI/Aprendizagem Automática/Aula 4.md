## Árvore de Decisão - Algoritmo Supervisionado

- Constrói **modelos de regressão ou de classificação sob a forma de uma estrutura em árvore**.
- **Divide-se um conjunto de dados em subconjuntos cada vez mais pequenos, ao mesmo tempo que se desenvolve incrementalmente uma árvore de decisão associada**.
- O **resultado final** é uma árvore com nós de decisão e nós de folha. Um nó de decisão tem dois ou mais ramos cada um representando valores para o atributo testado. O nó de folha representa uma decisão sobre o alvo (classe ou valor que fica associada à amostra).
- O **nó de decisão mais alto de uma árvore**, que *corresponde* ao atributo considerado como melhor preditor é chamado nó raiz. As árvores de decisão podem lidar com dados tanto categóricos como numéricos.

### Como escolher o atributo preditor no nó de decisão ?

Vários métodos: Redução de Entropia, Gini, Desvio Padrão... •Visando um ganho de informação incremental

## Modelos Múltiplos

Não existe um algoritmo que seja o melhor para todos os problemas. 
	• No free lunch theorem. 
• Algoritmos diferentes:
	- Diferentes representações 
	- Diferentes funções de custo 
	- Diferente exploração/prospeção do espaço de procura

A aprendizagem de modelos múltiplos (**ensemble learning**) é um processo que usa um conjunto de modelos, cada um deles obtido pela aplicação de um processo de aprendizagem para um determinado problema. Estes modelos (conjunto) são integrados de alguma forma para obter a previsão final.

- Utilizados para :
	- Classificação;
	- Regressão;
	- Agrupamento;
- A combinação de modelos aumenta a complexidade, Em compensação e exatidão pode aumentar
- Violação do princípio da navalha de Ockham (Ockham’s razor: simplicity leads to greater accuracy)