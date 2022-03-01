# ENEM-2016 - Análise, Engenharia e Predição de Dados

Trabalho prático da disciplina optativa de INtrodução à Ciência dos Dados da 🏫 Universidade Federal de Viçosa - Campus Florestal. 

Este trabalho teve como objetivo aplicar diversas técnicas de exploração e engenharia de atributos para desenvolver um modelo capaz de prever as notas das provas do ENEM de 2016 usando a Regressão Linear. 

## 💻 Resultados 

Os atributos usados na criação do primeiro modelo foram categorizados e são eles: Idade, Sexo, Raça, Ano de Conclusão do Ensino Médio, Escolaridade da Mãe, Classe Social, Disponibilidade de Internet, Tipo de Ensino Médio e Estado Civil. 

Prova | $R^2$ | MAE | MSE
--- | --- | --- | ---
Matemática | 0.24 | -71.31 | -8156.24 |
Linguagens e Códigos | 0.17 | -49.76 | -3903.22 |
Ciências Humanas | 0.20 | -52.84 | -4411.94 |
Ciências da Natureza | 0.25 | -50.61 | -4005.50 |
Redação | 0.17 | -102.49 | -19515.30 |
Nota Média | 0.30 | -48.77 | -3900.58 |

Em seguida diminuimos a quantidade de atributos usados para a criação do modelo (Classe Social, Internet e Ensino Médio) e obtivemos os seguintes resultados.

Prova | $R^2$ | MAE | MSE
--- | --- | --- | ---
Matemática | 0.20 | -73.21 | -8579.93 |
Linguagens e Códigos | 0.16 | -50.26 | -3972.84 |
Ciências Humanas | 0.18 | -53.56 | -4520.76 |
Ciências da Natureza | 0.22 | -51.50 | -4141.82 |
Redação | 0.14 | -104.47 | -10366.35 |
Nota Média | 0.27 | -49.66 | -4046.84 |


********************************************


## 🚀 Começando

Para obter uma cópia deste projeto:

```shell
git clone https://github.com/adrianomqsmts/enem-2016
cd enem-2016
```

## 🛠️ Construído com

Ferramentas, linguagens e outras tecnologias usadas no desenvolvimento deste sistema.

* [Anaconda](https://www.anaconda.com/) - Ambiente de Desenvolvimento
* [JupyterLab](https://jupyter.org/documentation) - Ambiente de Desenvolvimento
* [Python3](https://docs.python.org/3/) - Linguagem de Programação
* [Seaborn](https://seaborn.pydata.org/tutorial.html) - Visualização de Dados
* [Pandas](https://pandas.pydata.org/docs/) - Biblioteca para Dados Estruturados e Análise de Dados
* [cross_val_score](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_val_score.html#sklearn.model_selection.cross_val_score) - Para a validação cruzada do modelo
* [Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) - Para a criação do Modelo
* ...

## ✒️ Autores

* **Desenvolvedor** - *Código e Documentação* - [Adriano](https://github.com/adrianomqsmts)
