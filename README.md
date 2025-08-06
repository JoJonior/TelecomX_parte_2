# Telecom X - Parte 2

Este projeto tem como objetivo identificar os principais fatores que influenciam o cancelamento de clientes na empresa **Telecom X**. A partir de dados históricos, foram aplicadas técnicas de análise exploratória, pré-processamento e modelos de machine learning para prever a evasão de clientes e auxiliar na tomada de decisões estratégicas.

## Tecnologias utilizadas:

Python • Pandas • NumPy • Matplotlib • Seaborn • Scikit-learn • Jupyter Notebook


## 🧠 Problema

A Telecom X apresenta um alto índice de cancelamentos. Este estudo visa compreender os motivos por trás dessa evasão e sugerir ações baseadas em dados para reduzir esse número.

---

## 📊 Etapas do Projeto

1. **Importação e limpeza dos dados**
   - Carregamento do dataset
   - Verificação de valores nulos e tratamento

2. **Análise Exploratória (EDA)**
   - Distribuição de variáveis
   - Correlações entre variáveis
   - Análise de clientes que cancelaram vs. os que permaneceram

### Distribuição de Evasões (Dados Desbalanceado)
!["Distribuição de Evasões"](./OUTPUT/churn_distribution.png)

### Tempo de permanência × Evasão
!["Tempo de permanência x Evasão"](./OUTPUT/Tenure_churn.png)
### Total gasto × Evasão
!["Total Gasto x Evasão"](./OUTPUT/Charges_churn.png)
### Dispersão de Evasão por Tempo de permanência e Total gasto
!["Tempo de permanência x Evasão"](./OUTPUT/Charges_ternure_scatter.png)

### Matriz de Correlação
!["Matriz de Correlação"](./OUTPUT/Correlation_Matrix.png)
### Correlação com Evasão (Grafico em Barra)
!["Correlação com Evasão (Grafico em Barra)"](./OUTPUT/correlation_churn_only.png)

3. **Pré-processamento**
   - Codificação de variáveis categóricas
   - Normalização de dados (apeas para KNN,Regressão Logística)
   - Balanceamento da base (SMOTE)
Como visto na distribuição de evasão, os dados estão desbalanceados. Para melhorar o desempenho do modelo, apliquei a técnica de balanceamento oversampling **SMOTE**.
### Decision Tree PLOT
### Sem Balanceamento [3298,1334] x Com Balanceamento [3298,3298]
<div align="center">
<img src="./OUTPUT/_tree_No_Balance.png" alt="Sem Balanceamento 3298,1334">
<img src="./OUTPUT/_tree_Balance.png" alt="Com Balanceamento 3298,3298" >
</div>

4. **Modelagem**
   - Algoritmos utilizados:
     - Decision Tree
     - Random Forest
     - Regressão Logística
     - KNN
   - Avaliação das métricas:
     - Acurácia
     - Precisão
     - Recall
     - F1-score
5. **Visualizações**
   - Gráficos comparativos das métricas
   - Matriz de confusão
### Modelo 1 - Decision Tree
!["Matriz de Confusão Decision Tree"](./OUTPUT/ConfusionMatrix_Decision_Tree.png)
#### Score
- Treino: 0.80%
- Teste: 0.75%
### Modelo 2 - Random Forest
!["Matriz de Confusão Random Forest"](./OUTPUT/ConfusionMatrix_random_forest.png)
#### Score
- Treino: 0.83%
- Teste: 0.74%
### Modelo 3 - Regressão Logística
!["Matriz de Confusão Regressão Logística"](./OUTPUT/ConfusionMatrix_Logistic%20Regression.png)
#### Score
- Treino: 0.59%
- Teste: 0.74%

### Modelo 4 - KNN
!["Matriz de Confusão KNN"](./OUTPUT/ConfusionMatrix_KNN.png)
#### Score
- Treino: 0.50%
- Teste: 0.71%

### Comparação de Modelos
!["Comparação deas Metricas dos Modelos"](./OUTPUT/comparacao_modelos_machinelearning.png)

## Variaveis impactantes por cada Modelo 
### Regressão Logística
!["Importances Regressão Logística"](./OUTPUT/Regressão%20Logística_importance.png)
### Decision Tree
!["Importances Decision Tree"](./OUTPUT/Decision%20Tree_importance.png)
### Random Forest
!["Importances Decision Tree"](./OUTPUT/Random%20Forest_importance.png)

6. **Conclusões**
   - O modelo com melhor desempenho foi o **Random Forest**, destacando-se pela F1-score.
   - As variáveis com maior impacto na previsão do cancelamento foram:
     - Tipo de contrato
     - Utilização de serviços adicionais
     - Tempo de permanência

---



## Fatores que afetam a evasão de clientes
A análise conduzida revelou que os principais fatores que influenciam a evasão (churn) de clientes da TelecomX são:

* Contrato: Clientes com contratos mensais apresentaram maior probabilidade de evasão.

* Serviços adicionais: Usuários que não utilizam serviços como segurança online ou backup de dados mostraram maior tendência ao churn.

* Cobrança eletrônica: Clientes que utilizam fatura eletrônica tiveram uma taxa de evasão mais alta.

* Suporte técnico e atendimento: Sinais de insatisfação com suporte também correlacionaram-se com maiores índices de cancelamento.

## Estratégias de retenção propostas
Com base nas variáveis mais influentes e nos insights obtidos, propõem-se as seguintes estratégias:

* Incentivar contratos anuais: Oferecer vantagens (como descontos ou benefícios exclusivos) para migração de contratos mensais para anuais.

* Promoção de serviços adicionais: Criar campanhas de engajamento para destacar a importância dos serviços de segurança online, backup e suporte técnico, mostrando valor ao cliente.

* Revisar comunicação eletrônica: Avaliar a clareza e eficácia das cobranças digitais, incluindo linguagem, formato e frequência.

* Programa de fidelidade e atendimento personalizado: Implementar ações específicas para clientes com perfil de risco, como descontos, ligações preventivas e suporte prioritário.


