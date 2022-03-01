# Séries Temporais 

- Séries temporais são uma séries de observações registradas em intervalos de tempo regulares.
- Já parou para pensar na dificuldade de interpretar gráficos ou números que têm sazonalidade, ou seja, que não seguem o mesmo padrão ao longo do ano?
- Uma loja de varejo vai vender muito mais no natal do que no carnaval, isso é intuitivo para nós. Mas como identificar esse comportamento em gráficos? Como fazer uma previsão com isso?
- Normalmente, se usa o conceito de séries temporais para:
    - Identificar a natureza do fenômeno representado pela sequência de observações para encontrar padrões de comportamentos
    - Usar modelos estatísticos para prever valores futuros, baseando-se em resultados do passado.
- Como exemplos de fenômenos que podem ser acompanhados e registrados ao longo do tempo estão:
    - Movimentação do preço de ações na Bolsa de Valores.
    - Tamanho da população de uma cidade, estado ou país.
    - Vendas trimestrais de uma loja de varejo no segmento da moda.
    - Consumo de energia elétrica de um condomínio de casas.
    - Demanda de passageiros de uma companhia aérea ao longo do ano.

## Componentes de uma Série Temporal

- **Observação Original** - Ou seja, o gráfico original com os dados ao longo do tempo 
- **Tendência** - É a direção geral de alguma coisa que está se desenvolvendo ou evoluindo no eixo do tempo.
- **Sazonalidade** - É qualquer mudança ou padrão previsível em uma série temporal.
    - Essa oscilação pode ser recorrente ou se repetir ao longo de um determinado período de tempo. Dependendo o ruído nos dados obtidos, também é facilmente detectada em gráficos.
- **Ruído** - É a sobra das partes (componente aleatório)

## Séries Estacionarias

Uma série estacionaria são série que não possui uma tendencia, ou seja, não possuem um crescimento ou decréscimo, elas não tem também grande variância na media ao longo do seu período. Portanto é considerado uma série estacionaria aquela série que em certos períodos possui a mesma média. 

Algumas técnicas como Dickey-Fuller, KPSS e Philips-Perron são utilizadas para identificar se determinada série é estacionaria. É possível também aplicar funções logarítmica para transformar os dados e gerar um resultado com uma maior suavização tornando os dados mais estacionários.

Por fim pode-se aplicar também a técnica de diferenciação para deixar uma série estacionaria, que consiste em obter pequenos períodos da sua população ou amostra e aplicar a diferença entre eles tornando os dados mais próximos

## Séries Sazonais

No processo de decomposição de uma série temporal podemos encontrar uma parte dos dados que possuem um comportamento com grande variação mas que segue um padrão, ou seja, uma amostra dos dados que possui oscilação mas que essa oscilação se repete ao longo dos dados.

## Séries com Tendências

Uma série com tendencia como o próprio nome sugere, se trata de uma parte ou não da série temporal que possui um crescimento ou um decrescimento único e constante, quando esse crescimento ou decrescimento é ainda maior, chamamos de tendencia exponencial. Para tendencia temos também algumas técnicas para identificar o quanto determinado conjunto de dados é uma tendencia ou não, são eles o teste de Wald, Cox-Stuart, Mann-Kendall.

## Ruído de Uma série

O ruido ou resíduo é basicamente o que sobra de uma série temporal quando retiramos todos os aspectos listados acima, ou seja, tendencia e sazonalidade, em outras palavras o ruido é uma parte aleatória não correlacionada do conjunto de dados.

# ARIMA

- Um modelo ARIMA significa Média Móvel integrada AutoRegressiva
- Trabalha com a Média Móvel diante de dados históricos para prever o futuro, tanto com dados sazonais como dados não sazonais
- **Parâmetro P** associado ao AR do modelo (AR)IMA, é o parâmetro de regressão dos dados, ou seja, é ele que procura entender como esta se comportando os dados do passado.
    - Ordem da média móvel
- **Parâmetro D** associado ao I do modelo AR(I)MA, é o parâmetro que busca identificar uma especie de 'semelhança' nos dados, ou seja, a diferenciação entre os dados e com isso é possível saber se os dados tem uma grande variância o que contribui com o cenário de previsão.
    - Grau de Diferenciação
- **Parâmetro Q** associado ao MA do modelo ARI(MA), é o parâmetro da média móvel do modelo, em outras palavras ele que identificada através do calculo de média móvel a direção da tendência dos dados.
    - Ordem da parte autoregressiva
    
## Métricas

- Tem por objetivo minimizar os valores
- Akaike Information Criteria (AIC e AICc)
- Baysin Information Criteria (BIC)
- Buscar minimizar AIC e/ou BIC

## Auto.arime()

- Testa diferentes argumentos para **p**, **d** e **r**
- Extremamente Flexível

