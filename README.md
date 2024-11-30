# **Reconhecimento de Atividades Humanas usando K-means, PCA, t-SNE e DNN**

## **Objetivo**
O objetivo deste projeto é explorar técnicas de aprendizado de máquina para o reconhecimento de atividades humanas com base em dados coletados de sensores de dispositivos móveis. O foco principal está na aplicação do algoritmo **K-means** para agrupamento não supervisionado, utilizando métodos de redução de dimensionalidade como **PCA** e **t-SNE**, e na comparação com um modelo supervisionado, a **Rede Neural Profunda (DNN)**.

---

## **Descrição do Dataset**
- **Fonte:** Human Activity Recognition Using Smartphones (UCI Machine Learning Repository).  
- **Conteúdo:** Dados coletados de acelerômetros e giroscópios de smartphones.  
- **Atividades monitoradas:**
  - Caminhar
  - Subir escadas
  - Descer escadas
  - Sentado
  - Ficar em pé
  - Deitado  
- **Tamanho do dataset:**
  - **Amostras:** 10.299 registros
  - **Features:** 561 variáveis contínuas

---

## **Metodologia**

### **1. Análise Exploratória de Dados (EDA)**
Realizamos uma análise detalhada para compreender o dataset, verificar a presença de dados ausentes e explorar correlações entre variáveis. Foram utilizadas visualizações como histogramas e gráficos de dispersão para entender a estrutura dos dados.

### **2. Redução de Dimensionalidade**
Para melhorar o desempenho dos modelos e facilitar a visualização dos clusters, foram aplicadas técnicas de redução de dimensionalidade:
- **PCA (Principal Component Analysis):**
  - Redução das 561 features para 2 componentes principais.
  - Permitiu visualizar os dados em um espaço bidimensional e simplificar o K-means.  
- **t-SNE (t-Distributed Stochastic Neighbor Embedding):**
  - Utilizado para capturar relações não lineares entre os dados e melhorar a separação visual dos clusters.

### **3. Agrupamento com K-means**
O algoritmo **K-means** foi utilizado para agrupar as amostras em **6 clusters**, correspondendo às 6 atividades humanas monitoradas. A escolha do número de clusters foi feita utilizando:
- **Método do Cotovelo (Elbow Method):** Identificou o ponto de inflexão em \(k = 6\).
- **Silhouette Score:** Avaliou a coesão e separação dos clusters.

### **4. Comparação com Rede Neural Profunda (DNN)**
Para comparar os resultados do agrupamento não supervisionado com um modelo supervisionado, foi treinada uma **DNN** utilizando os rótulos reais do dataset.  
- A rede neural foi configurada com camadas densas, ativação ReLU e Dropout para evitar overfitting.
- **Métricas principais:**
  - Acurácia no conjunto de teste: **94,69%**.
  - Relatório de classificação e matriz de confusão para avaliação detalhada.

---

## **Resultados**

### **K-means**
- **Silhouette Score:** 0.6086  
- **Adjusted Rand Index (ARI):** 0.5403  
- **Normalized Mutual Information (NMI):** 0.6611  

Os resultados mostraram que o K-means conseguiu agrupar atividades estáticas (como "Deitado" e "Sentado") com boa precisão, mas teve dificuldades em separar atividades dinâmicas (como "Subir Escadas" e "Descer Escadas").

### **t-SNE e PCA**
- O **PCA** simplificou os dados, mas teve limitações em capturar padrões complexos não lineares.  
- O **t-SNE** destacou relações locais e ajudou a visualizar clusters mais definidos, sendo particularmente útil para entender sobreposições entre atividades dinâmicas.

### **Rede Neural (DNN)**
- A DNN superou o K-means, alcançando uma alta acurácia de 94,69%.  
- Foi particularmente eficaz para atividades dinâmicas, onde o K-means apresentou sobreposição entre clusters.

---

## **Conclusão**
- O **K-means** é uma ferramenta útil para identificar padrões iniciais em dados não rotulados, mas apresenta limitações em tarefas complexas de reconhecimento de atividades humanas.  
- A comparação com a DNN destacou as vantagens de métodos supervisionados para classificação precisa, especialmente em cenários com rótulos disponíveis.  
- Técnicas como **t-SNE** demonstraram ser valiosas para entender a estrutura dos dados e os agrupamentos gerados.


