## Aprendizagem Supervisionada - Classificação
- **Classificação** - é o problema de atribuir novas observações à classe a que mais provavelmente pertencem 
	- com base num modelo de classificação contruído a partir de dados de treino etiquetados
	- A exatidão das classificações dependerá da eficácia do algoritmo escolhido, da forma como é aplicado, e da quantidade de dados úteis para treino
![[Pasted image 20221025200401.png]]

- O objetivo do algoritmo é aprender uma regra geral que mapeie corretamente as entradas com as saídas. Os dados de entrada podem ser divididos em dois grupos
	- *X* , os atributos (características) a serem utilizados na determinação da classe de saída
	- *Y* , o atributo para o qual se deseja fazer a predição do valor de saída
	- É comum particionar os dados de entrada (rotulados) em dois conjuntos: **conjunto de treino** que servirá de construir o modelo, e o **conjunto de teste** que servirá para verificar como o modelo se comporta com novos dados, para podermos ajustar o modelo para a construção da versão final
![[Pasted image 20221025200733.png]]


## Regressão Logística

- Método aplicado apenas para problemas de classificação
- Ajusta uma curva sigmoide aos dados binários. O modelo produz a probabilidade de uma variável alvo Y pertencer a uma determinada class.
- Pode também ser aplicada a qualquer número de categorias
- Podemos usar um modelo de regressão linear para o mesmo fim?
	- Este pode acabar por prever valores inferiores a 0 ou superiores a 1, o que não faz sentido. Em vez disso o modelo de regressão logística (ou logit) foi concebido para atribuir uma probabilidade (entre 0% e 100%) de Y pertencer a uma determinada classe.
![[Pasted image 20221025201306.png]]
![[Pasted image 20221025201358.png]]
Minimizada pelo método da descida do gradiente

![[Pasted image 20221025201421.png]]

## Máquinas de vetores de suporte
- Resolve o mesmo problema que a regressão logística - classificação com duas classes e produz um desempenho semelhante.
- É geometricamente motivado, em vez de ser conduzido por pensamento probabilístico
- Realiza um mapeamento não linear para transformar os dados de treino originais em uma dimensão maior, buscando ne