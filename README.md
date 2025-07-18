# Projeto de Análise de dados: Acidente Titanic
Repositório criado para a **[competição do Kaggle sobre o desatre do Titanic](https://www.kaggle.com/competitions/titanic)**

- Este é o histórico dos resultados, que pode ser encontrado em: [https://www.kaggle.com/gluna777/competitions](https://www.kaggle.com/gluna777/competitions)
<img src="https://github.com/gluna777/analise_titanic/blob/main/imagens/grafico_analise_titanic.JPG" />

## [Primeira Análise: Moldelo inicial](https://github.com/gluna777/analise_titanic/blob/main/analise_titanic.ipynb)
- Nesta fase, foi realizado apenas os procedimentos iniciais para testar o resultado sem aplicar nenhum tratamento ou engenharia de dados mais avançada.
  - Foi utilizado o **ydata-profiling**, uma biblioteca que gera um relatório completo do dataset com poucos comandos, permitindo uma visão geral dos dados.
  - Em seguida, as colunas com cardinalidade muito alta foram removidas, e os valores faltantes foram tratados substituindo-os pela média (variáveis numéricas) e pela moda (variáveis categóricas), e excluímos todas as colunas de texto.
  - Para a modelagem, três algoritmos foram aplicados: **Árvore de Decisão**, **KNN** (K-Vizinhos Mais Próximos) e **Regressão Logística**. A avaliação dos modelos foi feita com base na acurácia e na matriz de confusão.

O score público obtido no Kaggle foi: **0,66746, assim obtendo um percentual de aproximadamente 66,75% de acurácia**.

## [Segunda Análise: Tratamento das Variáveis de Texto](https://github.com/gluna777/analise_titanic/blob/main/analise_titanic2.ipynb)
- Nesta fase, o principal objetivo foi processar as variáveis de texto para incluí-las no modelo.
  - Para isso, as funções **lambda** e **OneHotEncoder** foram utilizadas para transformar os dados categóricos em formato numérico.
  - Foram usados os mesmos algoritmos da etapa anterior (**Árvore de Decisão, KNN e Regressão Logística**) para avaliação.

Score público no Kaggle: **0,76555, assim obtendo um percentual de aproximadamente 76,56% de acurácia.** Também houve um aumento notável em relção a análise anterior.

## [Terceira Análise: Análise de Negócio e Refinamento dos Dados](https://github.com/gluna777/analise_titanic/blob/main/analise_titanic3.ipynb)
- Aqui, buscamos um entendimento mais profundo dos dados para otimizar seu tratamento e melhorar os resultados.
### Principais ações realizadas:
- Ajuste de escala nas colunas **Age e Fare**.
- Análise das variáveis **SibSp** (irmãos/cônjuges) e **Parch** (pais/filhos), criando duas novas features:
- Total de familiares a bordo (SibSp + Parch).
- Passageiro viajando sozinho (booleano).
- Seleção das variáveis mais relevantes por meio de análise de correlação.

Os mesmos modelos foram aplicados, e o score no Kaggle subiu para: **0,77751, assim obtendo um percentual de aproximadamente 77,75% de acurácia.** Um pequeno aumento em relação a análise anterior.

## [Quarta Análise: Testando Novos Algoritmos](https://github.com/gluna777/analise_titanic/blob/main/analise_titanic4.ipynb)
- Todas as colunas foram mantidas (incluindo SibSp e Parch) e novos algoritmos foram testados:
  - **Regressão Logística** (mantida por ter bons resultados anteriores).
  - **RandomForest** (ensemble learning).
  - **MLPClassifier** (Redes Neurais).
O **MLPClassifier** obteve a melhor acurácia na validação, mas apresentou overfitting nos dados de teste, resultando em desempenho inferior ao da Etapa 3.

Score público no Kaggle: **0,72727, percentual de aproximadamente 72,73% de acurácia.**

## [Quinta Análise: Otimização com GridSearchCV](https://github.com/gluna777/analise_titanic/blob/main/analise_titanic5.ipynb)
- Para melhorar os resultados, foi utilizado **GridSearchCV** para encontrar os melhores hiperparâmetros para os três modelos testados na etapa anterior.
 - O **RandomForest se destacou**, porém o resultado da acurácia ainda foi menor do que o da etapa 3.

Score público no Kaggle: **0,77033, um percentual de aproximadamente 77,03% de acurácia.**







