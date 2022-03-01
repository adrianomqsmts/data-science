# Regras de Decisão

- Uma regra de decisão é uma simples instrução IF-THEN que consiste em uma condição (também chamada antecedente) e uma previsão
    -  se chove hoje e se for abril (condição), DEPOIS vai chover amanhã (previsão)
- Uma única regra de decisão ou uma combinação de várias regras podem ser usadas para fazer previsões.
- As regras de decisão seguem uma estrutura geral: SE as condições forem atendidas, faça uma certa previsão.
-  Sua estrutura IF-THEN se assemelha se assemelha à linguagem natural e à maneira como pensamos, desde que a condição seja construída a partir de características inteligíveis, o comprimento da condição é curto (pequeno número de pares combinados com um E) e não há muitas regras
    - Se uma casa tem mais de 100 metros quadrados e tem um jardim, então seu valor é alto. Mais formalmente: IF THEN . `low medium high size>100 AND garden=1 value=high`
- **São similares a uma árvore de decisão**
    - Analisar a base de dados e criar uma séries de regras (condições) para classificar
- **Representação de uma Regre**
$$IF f_1 AND f_2 AND ... AND f_L THEN Class = c_i$$
    
FONTE [REGRAS DE DECISÃO](https://christophm.github.io/interpretable-ml-book/rules.html)

## Regras X Árvores


- Compreensibilidade em ambas
- Pouco espaço de armazenamento
- Regras são mais lentos que árvores
- Em geral regras possuem resultados piores que as árvores

## Regras Múltiplas

- Uma **lista de decisão** introduz uma ordem às regras de decisão. Se a condição da primeira regra for verdadeira, por exemplo, usamos a previsão da primeira regra. Se não, vamos para a próxima regra e verificar se ela se aplica e assim por diante. As listas de decisão resolvem o problema da sobreposição de regras, retornando apenas a previsão da primeira regra na lista que se aplica.

- Um **conjunto de decisões** se assemelha a uma democracia das regras, exceto que algumas regras podem ter um poder de voto maior. Em um conjunto, as regras são mutuamente exclusivas, ou há uma estratégia para resolver conflitos, como a votação majoritária, que pode ser ponderada pelas exatidão das regras individuais ou outras medidas de qualidade. A interpretabilidade sofre potencialmente quando várias regras se aplicam.

## Algoritmos

- **OneR** aprende regras a partir de um único recurso. O OneR é caracterizado por sua simplicidade, interpretabilidade e seu uso como referência.
- A **cobertura sequencial** é um procedimento geral que aprende iterativamente as regras e remove os pontos de dados que estão cobertos pela nova regra. Este procedimento é usado por muitos algoritmos de aprendizagem de regras.
- **Listas de regras bayesianas** combinam padrões frequentes pré-minerados em uma lista de decisão usando estatísticas bayesianas. Usar padrões pré-minerados é uma abordagem comum usada por muitos algoritmos de aprendizagem de regras.

# Aprender regras a partir de um único recurso (OneR)

- É um dos algoritmos de indução de regras mais simples
- Apesar do nome OneR, que significa "Uma Regra", o algoritmo gera mais de uma regra: Na verdade, é uma regra por valor de recurso único do melhor recurso selecionado
-  OneR retorna um recurso para o qual uma ou mais regras de decisão são definidas. Essencialmente, como um simples classificador, ele encontra exatamente um recurso (e um ou mais valores de recurso para esse recurso) para classificar instâncias de dados.
- O algoritmo é simples e rápido:
    1. Discretize os recursos contínuos escolhendo intervalos apropriados.
    2. Para cada recurso:
        - Crie uma tabela cruzada entre os valores do recurso e o resultado (categórico).
        - Para cada valor do recurso, crie uma regra que prevê a classe mais frequente das instâncias que possuem esse valor de recurso específico (pode ser lida a partir da tabela cruzada).
        - Calcule o erro total das regras para o recurso.
    3. Selecione o recurso com o menor erro total.
- **Um modelo OneR é uma árvore de decisão com apenas uma divisão**. A divisão não é necessariamente binária como no CART, mas depende do número de valores de recursos únicos.
- **Observe que este algoritmo não é conhecido por seu bom desempenho de previsão**; assim, é bastante recomendado para fins de ensino e para linhas de base de desempenho mais baixas em aplicações do mundo real.

[Exemplo](https://christophm.github.io/interpretable-ml-book/rules.html#learn-rules-from-a-single-feature-oner)

## PRISM

- PRISM é um algoritmo de  inferência  de  regras  de  classificação,  muitas  vezes  mais  simples  e  confiáveis que as indiretamente inferidas por algoritmos de árvores de decisão
- Cria uma regra com múltiplos atributos, para cada uma das categorias. 
- Exemplo - Prever o risco em crédito
    - Se **?** Então risco = ALTO
        -  Devemos encontrar um atributo que preencha o espaço **?**. Devemos escolher o atributo que tiver a maior abrangência (quantidade) dentre os clientes que tiverem o risco ALTO.
    - Entao completa: Se Garantias = Nenhuma e **?** Então Risco = ALTO
        -  Devemos encontrar um atributo que preencha o espaço **?**. Devemos escolher o atributo que tiver a maior abrangência (quantidade) dentre os clientes que tiverem o risco ALTO. Mas desta vez, devemos excluir o atributo selecionado. 

