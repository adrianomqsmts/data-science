# Resumo

- Na classificação, calcula a probabilidade de um objeto ter determinado rótulo dadas algumas de suas características
- Precisamos estimar P(features | L)
    - “Naive” pois assume premissas simples (ex. dados seguem distribuição Normal)
- Rápido para treinar e classificar
- Poucos parâmetros para ajustar
- Fácil de interpretar os resultados
- **Útil para começar, para verificar se será necessários modelos mais complexos**
- **Funciona muito bem quando**
    - Dados são realmente representados pela premissa “Naive” (raro na prática)
    - Para categorias muito bem distintas
    - Para dimensões muito grandes dos dados, em que a complexidade do modelo não é relevante
    

# Aprendizagem Bayesiana

- O algoritmo 'Naive Bayes' é um classificador probabilístico baseado no “Teorema de Bayes”, o qual foi criado por Thomas Bayes (1701 - 1761) para tentar provar a existência de Deus.
- A principal característica do algoritmo, e também o motivo de receber 'naive' (ingênuo) no nome, é que **ele desconsidera completamente a correlação entre as variáveis (features)**. Ou seja, se determinada fruta é considerada uma 'Maçã' se ela for 'Vermelha', 'Redonda' e possui “aproximadamente 10cm de diâmetro”, o algoritmo não vai levar em consideração a correlação entre esses fatores, tratando cada um de forma independente.
- **Exemplos de Utilização**
    - Filtros de Spam
    - Mineração de emoções em uma frase (raiva, alegria, tristeza)
    - Separação de documentos
    - Previsões em tempo real: Por possuir uma velocidade relativamente alta e precisar apenas de poucos dados para realizar a classificação, o Naive Bayes pode ser utilizado para previsões em tempo real.
- **Correção Lapciana**
    - Evitar que hajam registros zerados, adicionando um registro a mais. (Evitando multiplicações zeradas)
- **Probabilidade a-priori**
    - Somente analisando a base de dados podemos chegar a alguma conclusão
    - Dados que já conhecemos
- **Probabilidade pos-priore**
    - É o resultado final da classificação
- **Vantagens**
    - Rápido
    - Simplicidade de interpretação
    - Trabalha com muitos atributos (fácil generalização)
    - Boas previsões em bases menores
- **Desvantagem**
    - Combinação de características (atributos independentes) - Cada par de características são independentes - nem sempre é verdade 

## Exemplo

Digamos que estamos trabalhando no diagnóstico de uma nova doença, e que fizemos testes em 100 pessoas distintas.

Após coletarmos a análise, descobrimos que 20 pessoas possuíam a doença (20%) e 80 pessoas estavam saudáveis (80%), sendo que das pessoas que possuíam a doença, 90% receberam Positivo no teste da doença, e 30% das pessoas que não possuíam a doença também receberam o teste positivo.

Listando esses dados de uma forma mais clara, temos:

- 100 pessoas realizaram o teste.
- 20% das pessoas que realizaram o teste possuíam a doença.
- 90% das pessoas que possuíam a doença, receberam positivo no teste.
- 30% das pessoas que não possuíam a doença, receberam positivo no teste.

A pergunta neste caso seria: Se uma nova pessoa realizar o teste e receber um resultado positivo, qual a probabilidade de ela possuir a doença?

O algoritmo de Naive Bayes consiste em encontrar uma probabilidade a posteriori (possuir a doença, dado que recebeu um resultado positivo), multiplicando a probabilidade a priori (possuir a doença) pela probabilidade de receber um resultado positivo, dado que tem a doença'. Devemos também computar a probabilidade a posteriori da negação (Não possuir a doença, dado que recebeu um resultado Positivo).

Ou seja:

- P(doença|positivo) = 20% * 90%
- P(doença|positivo) = 0,2 * 0,9
- P(doença|positivo) = 0,18
- P(não doença|positivo) = 80% * 30%
- P(não doença|positivo) = 0,8 * 0,3
- P(não doença|positivo) = 0,24

Após isso precisamos normalizar os dados, para que a soma das duas probabilidades resulte 1 (100%). Para isso, dividimos o resultado pela soma das duas probabilidades.

Exemplo:

    P(doença|positivo) = 0,18/(0,18+0,24) = 0,4285
    P(não doença|positivo) = 0,24/(0,18+0,24) = 0,5714
    0,4285 + 0,5714 = 0,9999.. ou aproximadamente 1.


A fórmula se apresenta desta maneira:

$$P(A|B) = \frac{P(B|A) * P(A)}{P(B)}$$

Podemos concluir que se o resultado do teste da nova pessoa for positivo, ela possui aproximadamente 43% (0,4285) de chance de estar doente.

## Tipos 

### Bernoulli Naive Bayes

Assume que todos os nossos recursos são binários, de forma que eles assumem apenas dois valores. Significa que 0s pode representar “a palavra não ocorre no documento” e 1s como “a palavra ocorre no documento”.

### Multinomial Naive Bayes

É usado quando temos dados discretos (por exemplo, classificações de filmes que variam de 1 a 5, pois cada classificação terá uma certa frequência para representar). No aprendizado de texto, temos a contagem de cada palavra para prever a classe ou rótulo.

### Gaussian Naive Bayes

Por causa da suposição da distribuição normal, Gaussian Naive Bayes é usado nos casos em que todos os nossos recursos são contínuos. Por exemplo, no conjunto de dados Iris, os recursos são largura da sépala, largura da pétala, comprimento da sépala e comprimento da pétala. Portanto, seus recursos podem ter valores diferentes no conjunto de dados, pois a largura e o comprimento podem variar. Não podemos representar recursos em termos de suas ocorrências. Isso significa que os dados são contínuos. Portanto, aqui usamos Gaussian Naive Bayes. 

FONTE COMPLETA : [1.9. Naive Bayes](https://scikit-learn.org/stable/modules/naive_bayes.html)


