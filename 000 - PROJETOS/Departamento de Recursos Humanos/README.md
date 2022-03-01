# Departamento de Recursos Humanos

Um projeto que analisa dados da competição [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset) no Kaggle e realiza a predição da probabilidade de um dado funcionário deixar a empresa, utilizando o histórico de dados do RH.

## Resultados

- **Logistic Regression** 

precision | recall | f1-score | support 
--- | --- | --- | --- |
0  | 0.87 | 0.97 | 0.91 | 298
1  | 0.74 | 0.36 | 0.48 | 70
accuracy  | - | - | 0.85
           
- **Random Forest**
  
precision | recall | f1-score | support 
--- | --- | --- | --- |
0  | 0.85 | 0.92 | 0.88 | 298
1  | 0.48 | 0.33 | 0.39 | 70
accuracy  | - | - | 0.82  
           
- **Rede Neural Artificial**
  
precision | recall | f1-score | support 
--- | --- | --- | --- |
0  | 0.83 | 0.98 | 0.90 | 298
1  | 0.62 | 0.14 | 0.23 | 70
accuracy  | - | - | 0.80 



## Bibliotecas

- pickle
- pandas
- numpy 
- seaborn 
- matplotlib.pyplot
- OneHotEncoder
- MinMaxScaler
- train_test_split
- LogisticRegression
- accuracy_score
- confusion_matrix
- ConfusionMatrixDisplay
- f1_score, precision_score, recall_score, classification_report
- RandomForestClassifier
- tensorflow 