## Viés e Variância

- Duas fontes de erro em qualquer projeto:
	- **Viés** (Bias) -> Taxa de erro do algoritmo no conjunto de treino
	- **Variância** (Variance) -> quão pior é a taxa de erro no algoritmo no conjunto de teste
- Associados a estas duas fontes de erro há dois grandes problemas que podem ser exibidos pelos classificadores
	- **Overfitting** -> Sobreajuste. Erro de treino muito baixo, mas não consegue generalizar para o conjunto de teste. Baixo viés, alta variância.
	- **Underfitting** -> Ajuste Deficitário. Erro do conjunto de teste apenas um pouco maior que o do treino que é muito assinalável. Alto viés, Baixa variância.
![[Pasted image 20221107153736.png]]

## Preparação de dados
Os dados podem ter de ser adaptados para que seja possível utilizar um determinado modelo.

- Limpeza. 
	- Suavizar (filtrar) os dados ruidosos. 
	- Identificar ou remover os valores aberrantes (ou anómalos ou discrepantes ou outliers). 
- Resolver incoerências. 
	- Normalização, discretização
- Preencher os valores em falta - imputação
