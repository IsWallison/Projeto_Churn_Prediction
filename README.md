# Projeto_Churn_Prediction
[![author](https://img.shields.io/badge/author-Wallison-red.svg)](https://www.linkedin.com/in/wallison-borges-48312516a/) [![](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/release/python-365/) [![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://perso.crans.org/besson/LICENSE.html) [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/IsWallison/Project_airbnb/issues)
<p align="center">
  <img src="4689578.jpg" >
</p>
Churn rate, ou simplesmente churn, representa a taxa de evasão da sua base de clientes. Em serviços como Spotify ou Netflix, ela representaria a taxa de cancelamento de assinaturas.
Ela é de extrema importância para a administração e sua análise ao longo do tempo pode mostrar que existe algum problema que deve ser atacado.
Churn também pode ser usado para identificar potenciais cancelamentos, com um tempo de antecedência, e promover ações direcionadas para tentar reter tais clientes. Essa métrica deve receber atenção pelo fato de que o Custo de Aquisição de Cliente (CAC) é normalmente mais alto que o custo para mantê-los. Ou seja, um alto valor para o churn rate é o que não desejamos.

# Dataset
O conjunto de dados pode ser facilmente encontrado aqui: https://raw.githubusercontent.com/carlosfab/dsnp2/master/datasets/WA_Fn-UseC_-Telco-Customer-Churn.csv

# Bibliotecas necessárias
* Pandas
* Matplotlib
* Seaborn
* scikitplot
* numpy
* sklearn (Vários pacotes)
* imblearn (RandomUnderSampler) 
Você também precisará de um software que possa executar um notebook python .ipynb


# 8 modelos foram utilizados para avaliar seu desempenho na base de dados.:

* SVC
* KNeighborsClassifier
* MLPClassifier
* GradientBoostingClassifier
* RandomForestClassifier
* DecisionTreeClassifier
* LogisticRegression
* GaussianNB

--------------------------
Model	| Recall|	Accuracy|	F1
-----|-----|-----|-----
GradientBoostingClassifier Scale	|0.798717	|0.768964	|0.015
LogisticRegression	|0.798008	|0.767538	|0.017
GradientBoostingClassifier	|0.793053	|0.766836	|0.015
LogisticRegression Scale	|0.791627	|0.766480	|0.019
SVC Scale	|0.794469|	0.763282	|0.022
GaussianNB	|0.811465	|0.761156	|0.019
GaussianNB Scale	|0.809338	|0.754783	|0.014
RandomForestClassifier Scale	|0.759752	|0.751953	|0.016
RandomForestClassifier	|0.751242	|0.749469	|0.013
SVC	|0.778886	|0.748060	|0.010
MLPClassifier	|0.780317	|0.743803	|0.012
MLPClassifier Scale |	0.767549	|0.741681	|0.017
KNeighborsClassifier	|0.805117	|0.740261	|0.017
KNeighborsClassifier Scale	|0.794477	|0.731390	|0.018
DecisionTreeClassifier	|0.708749	|0.704464	|0.010
DecisionTreeClassifier Scale	|0.685344	|0.683204	|0.006


# Conclusão
Dadas as características do problema e o desempenho durante as execuções anteriores, optei pela Regressão Logística.
A partir da aplicação dos parâmetros encontrados através da otimização dos hiperparâmetros, foi criado um modelo de regressão logística com C=0.1, fit_intercept=False, penalty=l1 e solver=liblinear.

Este modelo foi avaliado com os dados de teste e obteve um desempenho razoável, com uma precisão de 0.92 para a classe 0 e 0.51 para a classe 1, e um recall de 0.71 para a classe 0 e 0.84 para a classe 1. O f1-score ficou em 0.81 para a classe 0 e 0.63 para a classe 1, o que indica que o modelo tem um desempenho superior na identificação da classe 0. A acurácia geral do modelo ficou em 0.75, o que indica que ele acertou 75% das previsões.

O modelo ainda pode ser melhorado com ajustes finos nos hiperparâmetros ou com outras técnicas de machine learning.
