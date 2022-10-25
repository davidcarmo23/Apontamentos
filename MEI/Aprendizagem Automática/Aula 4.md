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
- Realiza um mapeamento não linear para transformar os dados de treino originais em uma dimensão maior, buscando nesta nova dimensão um hiperplano que separe os dados linearmente de forma ótima. Com um mapeamento apropriado (para uma dimensão suficientemente alta) os dados poderão ser sempre separados por um hiperplano. O SVM encontra este hiperplano usando vetores de suporte (exemplos do treino) maximizando a margem definida por estes
![[Pasted image 20221025201646.png]]

![[Pasted image 20221025201708.png]]
![[Pasted image 20221025201723.png]]
![[Pasted image 20221025201739.png]]

## Avaliação de classificadores
- A aprendizagem automática visa fazer com que as máquinas fiquem melhores em certas tarefas, aprendendo a partir dos dados
- Existem muitos tipos diferentes de sistemas de AA: supervisionados ou não, baseado em instâncias ou baseados em modelos
- Em um projeto de AA, os dados são reunidos em um conjunto de treino e o conjunto de treino serve de entrada para um algoritmo de aprendizagem

- Se o algoritmo é baseado num modelo, otimiza alguns parâmetros para ajustar o modelo ao conjunto de treino. Espera-se que venha a ser capaz de fazer **boas previsões sobre novos casos**

- Se o algoritmo é baseado em instâncias, apenas aprende os exemplos e generaliza para novas instâncias usando uma **medida de similaridade** para comparar com as instâncias aprendidas

- **O modelo não deve ser muito simples (nesse caso o ajuste será insuficiente) nem muito complexo (nesse caso terá sobreajuste)**

### Como avaliar um modelo
- **Avaliar um modelo é bastante simples: basta usar um conjunto de teste**

### Conjunto de validação
![[Pasted image 20221025202015.png]]

### Não há almoços à pala
![[Pasted image 20221025202050.png]]

### Validação do modelo
![[Pasted image 20221025202113.png]]

![[Pasted image 20221025202131.png]]


### Matriz de confusão
![[Pasted image 20221025202211.png]]

### Outras medidas d