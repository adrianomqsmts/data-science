# Introdução

- **Inteligência Artificial** 
    -  A Inteligência Artificial é a ciência e a engenharia de criar máquinas inteligentes, especialmente programas de computador inteligentes”
- **Aprendizado de máquina**
    - Algoritmos que usam dados históricos para ajudar nas tomadas de decisões.
- **Aprendizado profundo** 
    - Rede neural com múltiplas camadas. A aprendizagem profunda é uma das formas de executar o aprendizado de máquina
- **Mineração de Dados**
    - Extração de padrões em dados, para obter conhecimento
- **Big Data**
    - Volume (escala de dados), Velocidade (análise de dados de streaming), Variedade (diferentes tipo de dados) e Veracidade (incerteza de dados).
- **Ciência dos dados**
    - Envolve coleta, limpeza, preparação e análise de dados com o objetivo de extrair informações úteis ao negócio. 
    - Um cientista de dados precisa conhecer de programação, matemática, estatística e do negócio em si.
    - Um cientista de dados é melhor em estatística do que qualquer outro programador, e melhor em programação do que qualquer outro estatístico. - Josh Wills, Director of Data Engineering at Slack
    - Área multidisciplinar (Ciência dos dados, matemática e estatística, Regras do Negócio)
    - Etapas:
        - Coletar
        - Explorar
        - Limpar
        - Transformar
        - Modelar
        - Validar
        - Implantar (Volta ao início)
    - Conhecimentos importantes
        - Estatística
        - Bando de dados (Relacionais e não relacionais)
        - Sistemas Distribuídos
        - Processamento Paralelo
        - Computação em Nuvem
        - Machine Learning
        - Processamento de Linguagem natural
        - Escrita e Apresentação  
    

## Estatística Descritiva

- Os **DADOS** são os registros soltos, aleatórios, sem quaisquer análise (Rezende, 2015).
- A **INFORMAÇÃO** seria qualquer estruturação ou organização desses dados
- O **CONHECIMENTO** é a informação processada e transformada em experiência pelo indivíduo. O conhecimento é a capacidade que, o processamento da informação adicionado ao repertório individual, nos dá, de agir e prever o resultado dessa ação. 

### Objetivos de aprender estatística 

- Sintetizar enormes quantidades de dados
- Tomar decisões melhores: Pessoais e profissionais
- Avaliar criticamente notícias e estudos publicados
- Reconhecer padrões em diferentes setores de atuação: comportamento de clientes, fraudes, mobilidade urbana, etc.

### Por onde Começar

- Encontrar uma “medida do meio” ou “tendência central”
    - **Média** é uma estatística descritiva que deve ser usada com cuidado, pois a média é sensível a valores extremos (outliers), que são observações que se situam mais longe do centro
    - **Mediana**: ponto que divide a distribuição ao meio, significando que metade das observações está acima da mediana, e metade abaixo. A mediana não é sensível a pontos extremos (outliers) e para distribuições sem valores extremos, a mediana e a média serão similares
    - **Quartis**: 4 partes de 25%. Ex: Se sua renda está no último quartil (75%), você ganha mais que 75% da população
    - **Decis**: 10 partes de 10%. Ex: sua renda está no primeiro decil (10%), você ganha menos que 90% da população
    - **Percentis**: 100 partes de 1%. Ex: Se sua renda está no último percentil (99%), você ganha mais que 99% da população
    - **Moda**: valor com maior frequência na distribuição
    - **Mínimo**: menor valor da distribuição
    - **Máximo**: maior valor da distribuição
- **Desvio padrão**: medida de como os dados se dispersam em relação à média, medindo o quanto as observações estão espalhadas. Assim, o desvio padrão é a estatística descritiva que nos permite atribuir um número único a essa dispersão em torno da média.
- A **Distribuição Normal**. Dados são simétricos em torno de sua média, em um formato de sino
- **Porcentagem** = (VALOR NOVO – VALOR ORIGINAL) / VALOR ORIGINAL.

### Histogramas

- Representação gráfica da distribuição de frequências de um conjunto de dados (Pode ser por valores absolutos ou frequências relativas). Pode separar os valores possíveis em classes para dados contínuos ou discretos.

### População X amostra

- Uma **população** é um conjunto de pessoas, itens ou eventos sobre os quais você quer fazer inferências. Nem sempre é conveniente ou possível examinar todos os membros de uma população inteira, por isso devemos selecionar uma amostra.
- Uma **Amostra** é um subconjunto de pessoas, itens ou eventos de uma população maior que você coleta e analisa para fazer inferências. Para representar a população bem, uma amostra deve ser coletada aleatoriamente e ser adequadamente grande.
    - Se a amostra é aleatória e grande o suficiente, você pode usar as informações coletadas a partir da amostra para fazer inferências sobre a população.

## Métodos Preditivos

### Classificação 

Resume em definir classes (rótulos) para os registros. Prever a classe. exemplos: 

- Marketing direto: comprar ou não o produto.
- insatisfação: satisfeito, insatisfeito, neutro.
- Risco de crédito: Aparenta risco alto, médio ou baixo de oferecer um empréstimo.
- Filtros de SPAM : Spam, promoção, membros de famílias etc.
- Separação de notícias: Esportes, economia, tecnologias, etc.
- Reconhecimento de voz ou face: Pessoas A, pessoas B ou C.



### Regressão

Resume em prever valores numéricos

- Gastos propagando -> valor de venda
- Temperatura, umidade e pressão do ar -> velocidade do vento
- Fatores externos -> valor do dólar
- Resultados do exame -> probabilidade de um paciente sobreviver
- Risco de investimento
- Gasto no cartão de crédito -> limite

## Métodos descritivos

### Associação

Resume em associar diferentes objetos

- Se comprar um produto A, existe uma chance de comprar o produto B
- Comprar cerveja aumenta a chance de comprar cerveja. 
- Prateleiras de mercado
- Promoção com itens que são vendidos em conjunto
- Planejar catálogos das lojas e folhetos de promoções
- Controle de evasão em universidades

### Agrupamento

Resume em analisar dados e encontrar grupos

- Segmentação de mercados: Mandar propagandas certas para o grupo certo
- Encontrar grupos de clientes que irão comprar um produto
- Agrupamento de documentos/notícias
- Agrupamento de produtos similares 
- Perfis de clientes: melhorar recomendações
- Análise de redes sociais

### Detecção de desvios (outliers)

Resume encontrar desvios (dados fora da margem)

- Detecção de fraudes de créditos: Compras fora do padrão
- Instrução em redes
- Uso de energia elétrica, água ou telefone: Roubo de energia ou vazamentos
- Desempenhos de atletas (doping)
- Monitoramento de máquinas em um data center

### Descoberta de padrões sequenciais

Prevê a chance de acontecer uma coisa após a outra. Ex: Comprou o primeiro livro do Harry Potter, tem uma chance de um tempo depois comprar o segundo ou terceiro livro. 


- Livrarias, lojas de atletismos, computadores
- Marketing direcionado para pessoas que tem maiores chances de maiores de adquirir um novo produto
- Prevenção de doenças
- Navegação de sites

### Sumarização

Resume em resumir um texto maior.

- São ouvintes de programas homens na faixa de 25 a 35 anos, com nível superior e que trabalha na área de administração
- Segmentação de mercado

## Tipos de aprendizado de máquinas

### Supervisionada (métodos preditivos)

Fase 1
1. Extração de características 
2. Algoritmo de aprendizagem: Supervisor que irá classificar cada um das entradas no algoritmo.
3. Modelo aprendido

Fase 2
1. Extração de Características
2. Modelo Aprendido 
3. Prevenção

### Não supervisionada (métodos descritivos)

Analisar automaticamente os dados (associação, agrupamento)
Necessita análise para determinar o significado dos padrões encontrados; 

Na aprendizagem supervisionada, o programa é treinado a partir do conhecimento de um supervisor e um conjunto de dados pré-definidos. Por outro lado, na aprendizagem não-supervisionada o programa encontra automaticamente padrões e relações em um conjunto de dados.

### Reforço

- Aprender com as interações com o ambiente (causa e efeito)
- Aprender com sua própria experiência 
- Robô coletando lixo aprendendo a andar em um ambiente
