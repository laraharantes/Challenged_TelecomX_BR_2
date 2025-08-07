# 📊 Telecom X – Parte 2: Previsão de Evasão de Clientes (Churn)

Este projeto corresponde à **Parte 2 do primeiro challenge Telecom X BR da Alura**. O objetivo é desenvolver modelos preditivos capazes de **identificar clientes propensos a cancelar seus contratos** com uma empresa de telecomunicações. 

A partir de uma base de dados com características demográficas, contratuais e de uso, foram aplicadas técnicas de **análise exploratória, engenharia de atributos, balanceamento de classes e machine learning supervisionado** para criar soluções com potencial aplicação real na retenção de clientes.

---

## 🧠 Técnicas e Etapas Utilizadas

### 1. 📁 Preparação e Limpeza dos Dados
- Remoção de valores ausentes e inconsistências
- Conversão de variáveis categóricas em numéricas (encoding)
- Criação de novas variáveis por engenharia de atributos (ex: `uso_streaming`, `longo_contrato`, `gasto_mensal_estimado`)
- Padronização e normalização das variáveis numéricas

### 2. ⚖️ Balanceamento de Classes
- Aplicação do **SMOTEENN** para equilibrar a distribuição entre clientes que evadiram (`1`) e os que permaneceram (`0`)
- Redução de ruído nos dados com o método ENN (Edited Nearest Neighbors)

### 3. 🧪 Treinamento de Modelos
- **Regressão Logística**
- **Random Forest**

> Modelos como KNN e SVM foram considerados, mas os melhores resultados foram obtidos com Random Forest e Regressão Logística.

### 4. 🔧 Otimização de Hiperparâmetros
- Aplicação de `GridSearchCV` com validação cruzada (5-fold) para ajustar os hiperparâmetros dos modelos

### 5. 📈 Avaliação de Desempenho
- Acurácia, Precisão, Recall, F1-score
- Matriz de Confusão
- Comparação entre treino e teste (verificação de overfitting)

### 6. 🧬 Análise de Variáveis Relevantes
- **Random Forest:** Importância das variáveis com base na redução de impureza (Gini)
- **Regressão Logística:** Interpretação dos coeficientes para entender o impacto positivo ou negativo na evasão

---

## ✅ Resultados

| Modelo               | Acurácia | Recall (Classe 1 – Evadido) | F1-Score (Classe 1) |
|----------------------|----------|------------------------------|----------------------|
| Regressão Logística  | 73.1%    | 81%                          | 0.61                |
| Random Forest        | 73.9%    | 82%                          | 0.63                |

- Ambos os modelos foram eficientes na detecção da evasão.
- O **Random Forest** teve ligeiro destaque em recall e F1-score para a classe dos evadidos.

---

## 🔍 Principais Fatores de Evasão

### Regressão Logística – Top Coeficientes
- `backup_online`, `seguranca_online`, `protecao_dispositivo`: fortemente associados à permanência
- `fatura_diaria`, `recursos_online`, `fatura_mensal`: associados à evasão

### Random Forest – Top Importâncias
- `meses_contrato`, `tipo_contrato_Two year`, `fatura_mensal`, `fatura_total`: variáveis com maior poder preditivo

---

## 💡 Estratégias de Retenção Sugeridas

1. **Oferecer pacotes combinados** com segurança, backup e entretenimento
2. **Reduzir a frequência de cobrança e melhorar a transparência das faturas**
3. **Incentivar contratos de longo prazo com benefícios** exclusivos
4. **Monitorar clientes com baixo tempo de contrato e alto gasto mensal**
5. **Criar alertas internos para segmentos de risco e campanhas personalizadas**

---

## 🛠️ Tecnologias Utilizadas

- Python 3.10+
- Pandas, NumPy, Matplotlib, Seaborn
- Scikit-learn, imbalanced-learn
- Jupyter Notebook

---

## 📂 Organização do Notebook

1. Extração e limpeza dos dados  
2. Engenharia de atributos  
3. Codificação de variáveis  
4. Normalização / Padronização  
5. Análise de proporções  
6. Correlação e análises direcionadas  
7. Balanceamento com SMOTEENN  
8. Treinamento e avaliação dos modelos  
9. Otimização com GridSearch  
10. Análise das variáveis mais importantes  
11. Estratégias de retenção

---

## 👨‍💻 Autoria

Desenvolvido por **[Larah Arantes]** como parte da **Parte 2 do Challenge Telecom X BR (Alura)** – Projeto de classificação binária para previsão de churn (evasão de clientes).

