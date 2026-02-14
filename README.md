Este projeto tem como objetivo aplicar técnicas de Machine Learning para detecção de fraudes em transações financeiras utilizando o dataset público disponibilizado pelo TensorFlow (creditcard.csv).

O foco foi testar diferentes profundidades de árvore de decisão e analisar o comportamento das métricas, principalmente o recall, já que em problemas de fraude é mais crítico deixar de identificar uma fraude real do que classificar uma transação legítima como suspeita.

Dataset

O conjunto de dados contém 284.807 transações financeiras com 30 variáveis numéricas (V1 a V28, Time e Amount) e uma variável alvo:

Class = 0 (transação normal)

Class = 1 (fraude)

O dataset é altamente desbalanceado, com baixa proporção de fraudes.

Metodologia

Separação entre variáveis preditoras (X) e variável alvo (y).

Divisão em treino (80%) e teste (20%).

Treinamento de um DecisionTreeClassifier variando o parâmetro max_depth de 1 a 29.

Avaliação utilizando acurácia e recall.

Plotagem das curvas de desempenho para treino e teste.

Resultados

Observou-se que:

A acurácia permaneceu muito alta em todas as profundidades devido ao desbalanceamento.

O melhor recall de teste ocorreu na profundidade 4 (0,8163).

A partir desse ponto, o recall de teste estabiliza enquanto o recall de treino continua aumentando, indicando overfitting.

Com base nisso, o ajuste fino de hiperparâmetros foi limitado a profundidades menores (5 e 6) para manter melhor capacidade de generalização.

Conclusão

O estudo mostrou que apenas aumentar a complexidade do modelo não melhora necessariamente o desempenho em dados reais. O controle da profundidade da árvore foi essencial para equilibrar recall e generalização no problema de detecção de fraudes.
