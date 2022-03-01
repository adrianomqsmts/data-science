# Dados
- Dados são uma coleção de **objetos com atributos**
- Um **atributo** (variável, campo, característica, coluna de dados, ou **feature**) é uma propriedade ou característica de um objeto
    - Ex: Cor dos Olhos, Temperatura, Estado Civil
- Uma coleção de atributos descreve um **objeto** (registro, ponto, entidade, instância ou linha de dados)
- **Dataset** é um conjunto de dados

## Atributos (features) 

- Propriedades ou características dos dados
- No formato bi-dimensional, como tabelas ou matrizes, cada atributo é uma coluna, e cada observação é uma linha
- O valor de um atributo representa uma propriedade ou característica de um objeto
- Cada linha é um vetor de atributos (feature vector ou vetor de características)
- Todos os atributos de todas as observações representam o conjunto de atributos
- A qualidade e a quantidade de atributos são relevantes para o desempenho do modelo a ser criado
- Podem ser extraídos diretamente dos dados brutos ou derivados

## Coleta de Dados

- Dados estão por toda a parte, em diferentes formatos, tamanhos e formas
- Podem vir de diferentes fontes como WEB, sistemas legados, banco de dados relacionais ou não, arquivos, dispositivos móveis, sensores, etc. 

## Formatos de dados

### CSV (Comma Separated Values)

- Por definição um CSV é um formato de arquivo 'comma-separated-values' (**valores separados ou delimitados por vírgulas**)
- Cada linha pertence a um dado, e cada vírgula separa um atributo de
- Atributos de diferentes tipos
- Cabeçalho opcional (às vezes começa com #)
- Cuidado com textos incluindo ','
- Cuidado com formatos numéricos (podem ter pontos, vírgulas, etc)

``` CSV
João,2018,Belo Horizonte
Maria,2019,Rio de Janeiro
```

### JSON (Java Script Object Notation)

- Formato de texto com conversões estabelecidas
- Suporta objetos, sendo tipado
- É um arquivo de fácil leitura, com tamanho reduzido. 

``` JSON
{
   "id":1,
   "nome":"Fulano",
   "endereco":"Ali"
}
```


### Parquet

- Baseado em colunas
- Eficiente nas comparações
- Filtragem nas colunas por meio de metadados
- Facilita recuperação de dados de colunas específicas
- **Um formato de arquivo muito mais eficiente que o CSV**

### XML (eXtensible Markup Language)

- Apesar de ultrapassado, ainda é muito usado
- Formato texto
- Estrutura de árvore, com uma raiz com vários galhos de elementos, cada um com seus próprios atributos e galhos. Os conteúdos são as folhas.

``` XML
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
</note>
```


### HTML

- HTML abreviação para a expressão inglesa HyperText Markup Language, que significa: "Linguagem de Marcação de Hipertexto"
- Similar ao XML
- Usada principalmente por navegadores Web
- Navegadores interpretam as tags para formatar os conteúdos para o usuário visualizar
- Porém, se o conteúdo é o que importa, é preciso usar outras técnicas para extrair

``` html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8"/>
        <title>Document</title>
    </head>
    <body>
        <!-- Conteúdo -->
    </body>
</html>
```

## Coleta de Dados

### APIs

- A sigla API refere-se ao termo em inglês "Application Programming Interface" que significa em tradução para o português "**Interface de Programação de Aplicativos**".
- API é um conjunto de rotinas e padrões de programação para acesso a um aplicativo de software ou plataforma baseado na Web. 


### Web Scraping

- Técnica para extrair conteúdo da Web, principalmente de páginas
- Automatizar processo de coleta de conteúdo Web
- **Envolve percorrer, analisar e extrair o conteúdo de uma ou várias páginas Web**
- Salvar conteúdo em formato que poderá ser  analisado mais facilmente
- Páginas dinâmicas e com controle de acesso (usuário/senha, Captcha) tornam o processo mais complicado
- Alguns navegadores possuem uma ferramenta de inspeção de HTML
- **Crawl**: faz requisições a servidores Web para recuperar as páginas Web de interesse. Sites podem manter um arquivo robots.txt para restringir acesso aos conteúdos
- Scrape: uma vez recuperados os dados puros das páginas, a tarefa de scraping visa extrair o seu conteúdo relevante. Pode utilizar expressões regulares, extração baseada em XPath, ou outras técnicas

### SQL

- **Dados armazenados em Banco de dados**
- Importante saber como fazer consultas eficientes em grandes volumes de dados (índices, partições, explain, joins, etc)

## Tipos de Atributos

### Numéricos

- informação escalar sobre os objetos
    - Ex. Número de visitas em um site, preço de um produto, peso de uma pessoa, etc.
- Base para vetores de várias dimensões, com um valor escalar por dimensão
- O valor, a faixa e a distribuição são características relevantes para os algoritmo

### Textos

- Conteúdo alfanumérico não-estruturado
- Pode conter estrutura gramatical (sintaxe) e significado (semântica) implícitas
- Requer cuidado especial no tratamento e entendimento

### Datas

- Permite valores informados como string ou números
- Indica um período de tempo
- Indica estação do ano, mês, ano, dia, horas, minutos, segundos, etc.

### Categórico

- Representa características que podem ser definidas por categorias
    - Ex. Cor de cabelo, Classe social, etc.
- Nominal: não há uma ordem entre as categorias
    - Ex. Cor do Cabelo pode ser “Preto”, “Branco”, “Marrom”
- Ordinal: há uma ordem entre as categorias
    - Ex. Classe social pode ser: “Alta”, “Média”, “Baixa”
- Atenção: podem ser definidas categorias com nomes em alfanuméricos ou apenas números, mas **operações matemáticas não são permitidas**

## Atributos Discretos X Contínuos

### Atributo Discreto

- Conjunto de valores finito ou contável
    - Ex. CEP, contagem de palavras em um texto
- Frequentemente representados como Inteiros

### Atributo Contínuo

- Conjunto de valores dos números Reais
    - Temperatura, altura, peso
- Frequentemente representados como variáveis de ponto flutuante

## Características

- Dimensão (número de atributos)
    - Desafio em lidar com dimensões muito grandes
- Tamanho (número de objetos)
    - Desafio em lidar com grandes volumes de dados (Big Data)

## Conjuntos de Dados

- **Registros**
    - Coleção de objetos, cada um composto de um conjunto fixo de atributos (Tabela Fixa)
- **Matriz**
    - Se os objetos possuem o mesmo conjunto fixo de atributos numéricos, então podem ser vistos como pontos em um espaço multidimensional, em que cada dimensão representa um atributo distinto
    - Matriz M x N, sendo M objetos e N atributos
- **Documento**
    - Um documento de texto pode ser visto como um vetor de termos
    - Cada termo é um componente (atributo) do vetor
    -  O valor de cada componente é o número de vezes que o termo correspondente ocorre no documento
- **Transação**
    - Tipo especial de registro, em que cada registro (transação) envolve um conjunto de itens
    - Ex: Compra em supermercado
- **Grafo**
    - Um grafo é um tipo abstrato de dados formado por vertices e arestas
