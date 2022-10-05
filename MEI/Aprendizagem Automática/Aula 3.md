# Programação Tradicional vs AA
**ML** -> The science of getting computer to learn without being explicitly programmed
![[Pasted image 20221005162918.png]]

## Quando usar AA ?
- Não existe perícia humana
- Os humanos não conseguem explicar a sua perícia
- Os modelos devem ser personalizados
- Os modelos são baseados em enormes quantidades de dados

## Aplicações de AA
- Anti-SPAM
- Procura na Web
- Sistemas de recomendação
- Reconhecimento de fala
- Visão Computacional

## Tipos de AA
- Aprendizagem **Supervisionada** -> Os dados de treino compreendem exemplos dos vetores de entrada junto com os seus vetores alvo correspondentes
	- **Classificação** -> o objetivo é atribuir a cada vetor de entrada um número finito de categorias discretas
	- **Regressão** -> a saída desejada consiste em uma ou mais variáveis contínuas

- Aprendizagem **não supervisionada** -> Os dados de treino consistem num conjunto de vetores x sem valores alvo ou rótulos associados
	- O objetivo pode ser descobrir grupos de exemplos semelhantes dentro dos dados (clustering)
	- ou determinar a distribuição de dados no espaço de entrada (estimativa de densidade)
	- ou projetar os dados para um espaço que permita a visualização

- Aprendizagem **semi-supervisionada** -> muitos dados de treino mas apenas uns poucos estão rotulados
- Aprendizagem **por reforço** -> o agente obtém recompensas advindas de uma sequência de ações

# Aprendizagem com Supervisão
Neste tipo de problemas partimos de um conjunto de dados com exemplos de treino e com etiquetas associadas

Por exemplo quando se aprende a classificar dígitos manuscritos, um algoritmo de aprendizagem supervisionado recebe milhares de fotografias de dígitos manuscritos, juntamente com etiquetas que indicam o número que cada imagem representa

O algoritmo aprenderá então a relação entre as imagens e os números associados, e aplicará essa relação aprendida para classificar imagens completamente novas (sem etiquetas) que a máquina nunca tinha visto antes

## Precisão é baixa, como melhorar o desempenho ?
- Arranjar mais dados
- Maior variação de dados relacionadas
- Treinar o algoritmo durante mais tempo
- Tentar outro algoritmo de aprendizagem
- Testar diferentes parametrizações
- Mudar a arquitetura do classificador (mais complexo/simples)

## Escala impulsiona a AA
![[Pasted image 20221005164843.png]]

## Preparação dos dados
- **Conjunto de treino** -> Utilizado para treinar o algoritmo de aprendizagem
- **Conjunto de desenvolvimento** -> Utilizado para ajustar parâmetros, selecionar recursos e tomar outras decisões sobre o algoritmo de aprendizagem. Também chamado de validação (cruzada).
- **Conjunto de teste** -> Para avaliar o desempenho do algoritmo
![[Pasted image 20221005165503.png]]

- Os conjus