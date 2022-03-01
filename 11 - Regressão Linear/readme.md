# Regressão Linear

- [Regressão Linear Simples: O Que é? Para Que Serve? Como Funciona?](https://oestatistico.com.br/regressao-linear-simples/)
- A **análise de regressão** avalia a amplitude da variação em uma variável, decorrente da variação em outra variável.
- A análise de análise de regressão nos permite
    - Quantificara relação entre uma variável e um resultado de nosso interesse, enquanto controlamos outros fatores
    - Podemos isolar o efeito de uma variável enquanto mantemos os efeitos das outras variáveis constantes
- Com base em dados conhecidos, **cria um modelo para prever valores contínuos de objetos desconhecidos**
- Regressão nos dá uma **estimativa da associação entre variáveis**, e não **prova**.
- **Objetivo**: encontrar um 'melhor encaixe' para uma relação linear entre duas variáveis
- A reta de regressão não descreve perfeitamente a relação entre as variáveis
- Uma das formas de avaliar a qualidade do ajuste do modelo é através do **coeficiente de determinação**. Basicamente, este coeficiente indica quanto o modelo foi capaz de explicar os dados coletados
    - O coeficiente de determinação define a porcentagem da variável dependente que é explicada pela variável explanatória

********
$$Y_i=\beta_0+\beta_1 x_i+\varepsilon_i,~~~\mbox{para }~i=1,\ldots,n,~~~~~(1.1.1)$$

- $Yi$ é uma variável aleatória e representa o valor da variável resposta (variável dependente) na i-ésima observação;
- $xi$ representa o valor da variável explicativa (variável independente, variável regressora) na i-ésima observação;
- $ϵi$ é uma variável aleatória que representa o erro experimental;
- $β0$ e $β1$ são os parâmetros do modelo, que serão estimados, e que definem a reta de regressão e
- $n$ é o tamanho da amostra.
*********

- Para qualquer coeficiente de regressão, temos 3 características importantes:
    - **Sinal** (positivo ou negativo): Sentido da associação
        - + Pessoas mais altas tendem a pesar mais
        - - Pessoas que exercitam mais pesam menos
    - **Tamanho**: efeito observado é relevante?
        - 0,8 quilos para cada centímetro de tamanho
        - R$86/ano para pessoas com dentes mais brancos
    - **Significância**: o resultado pode ser extrapolado para uma população
- **coeficiente de regressão** 
    - Resultado com base em uma amostra de dados, onde amostras diferentes podem levar a coeficientes diferentes
    - Para amostras grandes e representativas o coeficiente não oscilará muito de uma amostra para outra
    -  Podemos calcular o erro padrão do coeficiente
        - medida de dispersão entre várias amostras repetidas tiradas da mesma população
        - teorema central do limite: coeficientes estarão distribuídos normalmente em torno da “verdadeira” associação da população
        - Espera-se que mais da metade dos coeficientes se situem dentro de um erro padrão
        - Aproximadamente 95\% se situarão dentro de dois erros padrões
        
        ![regressao2.png](figuras\regressao2.png)
        
## Hipótese

- Podemos então testar a hipótese: não existe nenhuma relação entre a variável explicativa e a variável dependente  (coeficiente = 0)

## Análise de regressão multivariada

- Excelente ferramenta para encontrar padrões significativos em grandes e complexos conjuntos de dados

## Erros Comuns

1. Relação não linear - Não use regressão linear quando não houver relação linear entre as variáveis que você está analisando
2. Correlação x Causalidade - Regressão pode demonstrar uma relação entre duas variáveis, mas não prova se uma variável está causando a outra
3. Causalidade Reversa - Uma associação positiva entre A e B não prova que A causa B
    - Devemos ter razões para acreditar que as nossas variáveis explicativas afetam a variável dependente, e não o contrário
4. Viés da variável omitida - Análise de regressão não pode omitir variáveis relevantes para associação
    - idade x doenças, educação pais x educação filhos, renda x nível de violência, etc..
5. Variáveis explicativas correlacionadas - Usar uma ou outra variável, ou criar uma variável composta
6. Extrapolar para além dos dados - A inferência é relativa aos dados que foram usados
7. Excesso de variáveis - Só inclua variáveis com justificativa teórica
    - Risco de encontrar uma correlação significativa simplesmente pelo acaso, com uma variável fajuta e o pior, pesquisadores podem tentar justificar que essa variável fajuta faz algum sentido, depois do resultado
