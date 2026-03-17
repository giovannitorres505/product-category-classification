# product-category-classification
🇺🇸 English Version
Amazon Sales - Total Revenue Prediction
This project utilizes machine learning techniques to predict total sales revenue based on various product attributes. Using a dataset of 50,000 records, the model estimates financial outcomes with high precision.

Project Objective
The goal is to develop a regression model capable of estimating total_revenue with high accuracy to support financial planning and sales strategy.

Methodology

Exploratory Data Analysis (EDA): Analyzed revenue distribution and correlations between numerical variables.

Algorithm: RandomForestRegressor.

Features Used: price, discount_percent, quantity_sold, rating, and review_count.

Data Split: 80% of the data was used for training and 20% for testing.

Performance Metrics
The model demonstrated exceptional performance on the test set:

R² Score: ~0.9999, indicating the model explains nearly all the variance in the data.

Feature Importance: price (52.3%) and quantity_sold (44.5%) are the primary drivers of revenue.

Error Analysis: Direct comparison between real and predicted values shows minimal residual error.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


🇧🇷 Versão em Português
Previsão de Receita de Vendas - Amazon Dataset
Este projeto utiliza técnicas de aprendizado de máquina para prever a receita total de vendas com base em diversos atributos de produtos. Utilizando um dataset de 50.000 registros, o modelo estima resultados financeiros com alta precisão.

Objetivo do Projeto
O objetivo é desenvolver um modelo de regressão capaz de estimar a total_revenue (receita total) com alta acurácia para apoiar o planejamento financeiro e a estratégia de vendas.

Metodologia

Análise Exploratória de Dados (EDA): Análise da distribuição da receita e correlações entre variáveis numéricas.

Algoritmo: RandomForestRegressor.

Atributos Utilizados: price (preço), discount_percent (percentual de desconto), quantity_sold (quantidade vendida), rating (nota) e review_count (contagem de avaliações).

Divisão dos Dados: 80% dos dados para treinamento e 20% para teste.

Métricas de Desempenho
O modelo demonstrou um desempenho excepcional no conjunto de teste:

R² Score: ~0,9999, indicando que o modelo explica quase toda a variância dos dados.

Importância de Atributos: O preço (price - 52,3%) e a quantidade vendida (quantity_sold - 44,5%) são os principais influenciadores da receita.

Análise de Erro: A comparação direta entre os valores reais e as previsões mostra um erro residual mínimo.
