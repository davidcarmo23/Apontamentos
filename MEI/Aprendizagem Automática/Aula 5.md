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

- **Limpeza**
	- Outliers (erros de medição, má recolha de dados, ou condições de operação não consideradas ao recolher os dados) podem prejudicar a aprendizagem e ser fonte de erros
- Como Identificar?
	- padronização z-score (pontuação padrão), visualização (boxplot, scatter plot,...), métodos estatísticos (e.g. em modelos lineares pontos com alto erro residual), "classificação de uma só classe" (OCC, ie. treinar um modelo nos dados "normais", e depois prever se os novos dados recolhidos são normais ou uma anomalia)

- **Outliers** que fazer?
	- Nada (resistir à tentação de apagar, podem ser indicadores muito úteis, e.g. fraude bancária)
	- Impor limites (ou eliminar se manifestamente errados)
	- Discretização (dividir o âmbito de um atributo contínuo em intervalos)
		- Alguns métodos de aprendizagem requerem valores discretos, por exemplo, a maioria das versões do Naïve Bayes
		- Redução do tamanho dos dados para uma análise mais focada

- **Normalização**
	- Para métodos baseados na distância, ajuda a prevenir que atributos com grande amplitude de valores dominem os demais 
	- normalização min-max 
	- padronização z-score (pontuação padrão)

- **Imputação**
	- Utilizar uma constante global para preencher o valor em falta.
	- •Utilizar a média do atributo para preencher o valor em falta
	- Utilizar a média do atributo, para todas as amostras pertencentes à mesma classe, para preencher o valor em falta
