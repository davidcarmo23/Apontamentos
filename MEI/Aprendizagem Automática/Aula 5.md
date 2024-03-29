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
	- Utilizar o valor mais provável para preencher o valor em falta. Inferência de Bayes ou árvore de decisão •Identificar relações entre variáveis.
	- Regressão linear, Regressão linear múltipla, Regressão não linear 
	- Estimador de vizinhos mais próximos. Encontrar os k vizinhos mais próximos do ponto e preencher com o valor frequente ou o valor médio. Pode ser lento!

## Aprendizagem não Supervisionada

- Agrupamento por partição
- Agrupamento hierárquico
- Agrupamento difuso
- Critérios de validade de agrupamentos

### Clustering
- Processo de procura por um conjunto finito e discreto de estruturas de dados dentro de um conjunto variado finito de dados.
- Objetivo -> Partição dos dados em grupos em que os dados dentro são semelhantes entre si e diferentes de outros grupos.
- Two distinct, but complementary, facets are enclosed in this unsupervised learning task: 
	- the elicitation of a model of the overall structure of the data 
	- the pursuit for a manageable representation of a collection of objects into homogeneous groups

- Serve para :
	- Customer segmentation 
	- Focused data analysis 
	- Dimensionality reduction technique 
	- Anomaly detection (outlier detection) 
	- Semi-supervised learning 
	- Image search engines 
	- Image segmentation
- **Homogeneity**: Elements within a cluster are close to each other 
- **Separation**: Elements in different clusters are further apart from each other
	- …clustering is not an easy task!

### Clustering techniques
- **Hierarchical**
	- Organize elements into a tree, leaves represent genes and the length of the pathes between leaves represents the distances between genes. Similar genes lie within the same subtrees
- **Agglomerative**
	- Start with every element in its own cluster, and iteratively join clusters together 
- **Divisive**
	- Start with one cluster and iteratively divide it into smaller clusters 
- **Partitional**
	- Partitions the elements into a specified number of groups