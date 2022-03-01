# Qualidade dos Dados

- Se aplicarmos dados errados ou dados corretos para o problema errado, então os algoritmos podem gerar previsões erradas. 
    - "Entra lixo, sai lixo"
- Não se faz uma receita excelente com ingredientes estragados

## Entendimento dos Dados

-  Olhar para a forma dos dados
    - Quantos objetos?
    - Quantos atributos?
    - Quais os nomes dos atributos?
    - Qual o significado de cada atributo?
    - Quais os tipos dos atributos?
    
- Olhar para a ausência de alguns dados
    - Quais atributos possuem valores ausentes para algum objeto?
    - Quantos objetos possuem algum valor ausente?
    - Quais são os objetos que possuem algum valor ausente?
  
- Olhar para as estatísticas descritivas dos atributos numéricos
    - Qual a média e desvio padrão de cada atributo numérico?
    - Quais os percentis de cada atributo numérico?
    - Quais os valores mínimo e máximo de cada atributo numérico?
 
- Filtro dos dados
    - Selecionar apenas atributos relevantes
    - Selecionar apenas objetos com determinadas características
    
- Conversão de tipos
    - Datas de String para tipos apropriados para manipulação
    - Verificar separador de casas decimais
    
- Transformação
    - Criar novos atributos derivados (média de notas, dado das demais notas)
    - Criar novos atributos a partir de outras fontes
    - Alterar medida de acordo com demanda

## Problemas e Possíveis Soluções

### Ruídos

- Em objetos: objeto estranho
- Em atributos: modificação de valores originais
    - Distorção na voz ou imagem, precisão do GPS
- Muitas vezes é um problema comum que não interfere no resultado final
- Soluções: Método de Binning, Regressão ou Agrupamento

### Outliers

- São valores extremos
- São objetos com características diferentes da maioria dos outros
- **Podem ser bons ou ruins**
    - Outliers são ruídos que interferem na análise
    - Outliers são a meta a ser alcançada (Fraude em cartão de crédito, Detecção de intruso)

### Valores Ausentes

- Algum atributo de algum objeto com valor vazio
- informação não coletada (ex. pessoas não forneceram renda e idade, GPS desabilitado)
- Atributos podem não ser aplicáveis a todos os casos (ex. renda não se aplica a crianças)
- Dados ausentes podem confundir algoritmo e afetar resultado final
- Indicados por NaN, Null ou espaços vazios
- **Remoção de dados com pendência**
     - Dependendo da quantidade de dados, não irá atrapalhar
- **Inferência de valores para preenchimento**
    - Usar tendência central do atributo
    - Usar algum cálculo estatístico mais avançado
    - Preencher com valores de entidades similares (Grupos? Objeto anterior? Objeto posterior?)
    - Realizar uma média com os valores do mesmo atributo;
    - Realizar uma mediana com os valores do mesmo atributo;
    - Preencher o atributo faltante com os valores que mais ocorrem no dataset

### Dados Duplicados

- Mesmo objeto repetido ao longo dos dados
- Mesmo objeto, mas com detalhes diferentes. Ex. E-mail. 
- Não agregam valor
- Podem colocar viés no algoritmo
- **Na maioria dos casos, podem ser removidos**


### Dados Errados

- Podem ocorrer erros na coleta, como erros de digitação
- Importância de termos amostras grandes e significativas, para evitar que esses erros afetem os resultados
- **Na maioria dos casos, podem ser removidos**

### Dados com Viés

- Tendenciosos para alguma conclusão
- Ex: Previsão de votos coletados por telefone durante o dia, onde os trabalhadores não participarão da consulta.
- **Na maioria dos casos, podem ser removidos**

### Dados certos para o problema errado

- Dados foram coletados corretamente e estão completos, porém o conhecimento extraído é sem sentido do ponto de visto do negócio

### Dados Categóricos

- Alguns algoritmos só trabalham com atributos numéricos
- **Mapear em valor numérico**
    -  Cuidado pois, apesar de possíveis, operações matemáticas e estatísticas não farão sentido
- **Converter em colunas**
    - Cada atributo sendo uma coluna, com 0 ou 1 quando se  aplicar para cada linha (**One Hot Encoding**)
    
### Dados de Texto

- Tipo especial que requer tratamento especial
- **Tokenização**: separação em unidades consistentes  (ex. Palavras ou caracteres ou n-grams)
- **Remoção de Stop Words**: remover palavras que ocorrem muito frequentemente e que não carregam muita informação útil (ex. conjunções, artigos)
- **Stem (radical)**: converte palavras em sua forma canônica (Ex. Entregar, entregam, entregram → Entreg)


# Pré-processamento de dados

- Após cuidados dos dados com problemas, agora é a hora de prepará-los

## Agregação

- Combinar dois ou mais atributos (ou objetos) em um único atributo (ou objeto)
- Reduz o número de objetos ou atributos
- Mudança de escala (cidades agregadas em regiões, estados, países)
- Essa abordagem agrupa os dados semelhantes em um cluster. Os outliers podem ser tratados separadamente ou deixados de fora dos clusters.

## Amostragem

- Redução de dados, tanto na investigação preliminar quanto na análise final
- Uma amostragem é similar a todo o conjunto, desde que seja representativa(se tem aproximadamente as mesmas propriedades dos dados originais)
- Usualmente usada pois obter o conjunto completo (população) é inviável em termos de tempo e custo
- Útil para reduzir o custo computacional para processamento

### Tipos de Amostragem

- **Aleatória simples**
    - Probabilidade igual de selecionar qualquer item
    - Sem repetição ou com repetição
- **Amostragem estratificada**
    - Separação em partições
    
## Redução da Dimensão

- Pode ajudar a eliminar atributos irrelevantes (colunas)
- Reduzir tempo de processamento e memória
- Facilitar visualização
- **Técnicas**
    - Principal Component Analysis (PCA)
    - Singular Value Decomposition
    
## Seleção de Atributos

- Forma de reduzir dimensionalidade
- Remover atributos redundantes
    - Ex. preço unitário, quantidade e **preço total**
- Atributos irrelevantes que não agregam valor no processo de análise de dados
    -  Matrícula de estudante é irrelevante para predizer coeficiente

## Criação de Atributo

- Cria novos atributos que capturam informação mais relevante que os atributos originais
    - **Extração**: Ex. brilhos de imagens 
    - **Construção**: Ex. dividir massa por volume para ter densidade
    
## Discretização

- Converter atributos contínuos em discretos ou em categorias
- Mapear um conjunto potencial de valores em um conjunto pequeno de categorias e valores
- Comumente utilizada em classificação
- Discretização é o processo de colocar valores em buckets de modo que haja um número limitado de possíveis estados. Os próprios blocos são tratados como valores ordenados e discretos. Você pode discretizar tanto as colunas numéricos quanto as colunas de cadeia de caracteres.
- É o processo de transferência de funções contínuas, modelos, variáveis e equações em contrapartes discretas. Isso é importante, pois alguns algoritmos só trabalham com entradas de valores discretos, não conseguindo prever valores contínuos. A discretização cria um número limitado de possíveis estados.

## Dimensionamento de Categorias

- Função que mapeia um conjunto inteiro de valores de um atributo em um novo conjunto de valores, de tal forma que cada um dos valores antigos possa ser identificado como um novo valor
- Processo de transformação de dados numéricos
- **Variáveis em escalas diferentes contribuem de forma desbalanceada para o modelo**
- **Considerações**
    - Não se aplica a atributos categóricos transformados
    - Árvores de decisões não precisam de dimensionamento
    - Não necessariamente irá melhorar o modelo 
   
### Normalização - Min-Max

- Normalizar é padronizar a faixa de valores possíveis para um atributo numérico
- Valores muito espalhados podem afetar o algoritmo devido a medidas de distância utilizadas
- Várias técnicas para ajustar as diferenças entre atributos em termos de frequência de ocorrência, média, variância, etc
- Muda somente a escala dos dados, mas em visualizações o formato dos objetos continuam o mesmo. 
- **Usada quando**:
    - Transforma para scala comum entre 0 e 1
    - Quando não sabemos a distribuição dos dados
    - Quando precisamos de valores positivos
    - O algorítimo não requer dados normais. 
    - Queremos remover outliers, pois impõe limites. 

$$x = \frac{x - \min{x}}{\max{x} - \min{x}}$$

### Padronização - Z-Score

- Podem ter números negativos
- Não afetam outliers
- Deve ser usado na maioria dos casos
- Baseada na média e desvio padrão dos dado

$$x = \frac{x - mean(x)}{std(x)}$$
     
   
### Sumarização
- Preparar uma representação compacta dos dados
- Nesta ação novos atributos são gerados a partir do conjunto de atributos fornecido para ajudar no processo de mineração.
- Exemplos:
    - Estatísticas de um determinado atributo (soma, média, mediana, desvio padrão, etc)
    - Estatísticas de atributos agrupadas por categorias (soma por tipo de produto, média por gênero, etc)


## Codificação das Categorias

- Transforma categorias em números

## LabelEncoding

- Cada categoria irá receber um número
- Normalmente me ordem alfabética e começando pelo valor 0. 
- Ex: {A, B, C} -> {0, 1, 2}
- **Problema** -  O algoritmo pode correlacionar os dados como uma ordem de grandeza. 
- **Utilidade** 
    - Há ordem na categoria dos dados
    - Grande número de categorias

## One-hot encoding

- Cada categoria é transformada em um outro atributo (uma nova coluna.)
- Um valor binário informa a ocorrência. 
- Ex: {A, B, C} -> {1, 0, 0}, {0, 1, 0}, {0, 0, 1}
- **Problema**
    - **Dummy Variable Trap**
        - O valor dos atributos se tornam altamente previsíveis
        - Resulta em uma correlação entre as variáveis independentes. 
        - **Solução**: Excluir um dos atributos para diminuir a multicolinearidade. 
- **Utilidade** 
    - Não há ordem nas categorias dos dados
    - Poucas categorias
        
     