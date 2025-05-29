# Modelo de Previsão de Preços de Imóveis na Califórnia

Este projeto tem como objetivo construir um modelo de aprendizado de máquina para prever os preços de imóveis na Califórnia, utilizando o dataset de preços de imóveis do repositório StatLib, baseado no censo da Califórnia de 1990. O resultado deste modelo será utilizado para alimentar um sistema de análise e recomendação de investimento em imóveis.

A métrica de desempenho escolhida para avaliar o modelo é a **Raiz do Erro Quadrático Médio (RMSE)**.

Este projeto foi orientado pelo livro *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems* do autor *Aurélien Géron*.

## Estrutura do Projeto

O projeto é desenvolvido em um notebook Jupyter (ou Google Colab) e segue as seguintes etapas:

1.  **Importação de Bibliotecas**: Carregamento das bibliotecas Python necessárias para manipulação de dados, visualização e modelagem.
2.  **Download dos Dados**: Obtenção do dataset de preços de imóveis da Califórnia.
3.  **Análise Exploratória dos Dados (EDA)**:
    *   Visualização das primeiras linhas do dataset.
    *   Obtenção de informações gerais sobre os atributos (`.info()`).
    *   Análise dos valores únicos de atributos categóricos (`.value_counts()`).
    *   Resumo estatístico dos atributos numéricos (`.describe()`).
    *   Geração de histogramas para visualização da distribuição dos atributos numéricos.
4.  **Criação de um Conjunto de Testes**: Separação do dataset em conjuntos de treino e teste, utilizando amostragem estratificada para garantir representatividade das categorias de renda.
5.  **Visualização de Dados**:
    *   Plotagem da distribuição geográfica dos imóveis.
    *   Visualização da densidade populacional e preços médios em um mapa.
6.  **Busca por Correlações**: Análise da matriz de correlação entre os atributos numéricos e o preço médio do imóvel.
7.  **Teste de Novas Combinações de Atributos**: Criação de novos atributos combinando os existentes para identificar relações mais fortes com o preço médio do imóvel.
8.  **Tratamento dos Dados**:
    *   **Limpeza de Dados**: Tratamento de valores ausentes no atributo `total_bedrooms`.
    *   **Manipulação de Atributos Categóricos**: Conversão de atributos categóricos para formato numérico utilizando One-Hot Encoding.
    *   **Customização de Transformadores**: Criação de uma classe customizada para adicionar atributos combinados.
    *   **Transformação de Pipelines**: Criação de pipelines para automatizar o pré-processamento dos dados numéricos e categóricos.
9.  **Escolha e Treinamento de Modelos**:
    *   **Regressão Linear**: Treinamento e avaliação de um modelo de Regressão Linear.
    *   **Árvore de Decisão (para regressão)**: Treinamento e avaliação de um modelo de Árvore de Decisão.
    *   **Florestas Aleatórias (para regressão)**: Treinamento e avaliação de um modelo de Florestas Aleatórias.
10. **Aperfeiçoamento de Modelos Promissores**:
    *   **Grid Search**: Utilização de Grid Search para encontrar a melhor combinação de hiperparâmetros para o modelo de Florestas Aleatórias.
    *   **Análise dos Melhores Modelos**: Análise da importância dos atributos no modelo final.
11. **Avaliação do Sistema no Conjunto de Testes**: Avaliação do desempenho do modelo final no conjunto de testes e cálculo do intervalo de confiança para o erro de generalização.

## Dataset

O dataset utilizado é o **Conjunto de Dados de Preços de Imóveis da Califórnia** do repositório StatLib, baseado no censo da Califórnia de 1990. Os atributos incluem:

*   `longitude`
*   `latitude`
*   `housing_median_age` (idade média do imóvel)
*   `total_rooms` (número de cômodos)
*   `total_bedrooms` (número de quartos)
*   `population` (população)
*   `households` (famílias)
*   `median_income` (renda média)
*   `median_house_value` (valor médio do imóvel - **atributo alvo**)
*   `ocean_proximity` (proximidade do mar - atributo categórico)

## Como Executar

Para replicar este projeto, você pode:

1.  Clonar este repositório.
2.  Abrir o notebook Jupyter (ou no Google Colab).
3.  Executar as células sequencialmente.

## Resultados

Após o treinamento e ajuste dos modelos, o modelo de Florestas Aleatórias com hiperparâmetros otimizados apresentou o melhor desempenho no conjunto de testes. O **RMSE final obtido foi de 48424.96**.

## Próximos Passos

Alguns passos futuros para aprimorar este projeto incluem:

*   Explorar outros modelos de regressão.
*   Realizar engenharia de atributos mais avançada.
*   Ajustar ainda mais os hiperparâmetros com técnicas como Random Search.
*   Implementar validação cruzada aninhada para uma avaliação mais robusta.

## Tecnologias Utilizadas

*   Python
*   Pandas
*   NumPy
*   Matplotlib
*   Scikit-learn
