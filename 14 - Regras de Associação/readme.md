# Regras de Associação 

- **regras de associação** são usadas para descobrir elementos que ocorrem em comum dentro de um determinado conjunto de dados
- Existem diversos **algoritmos** que realizam buscas de regras de associação em bases de dados. Abaixo seguem alguns exemplos:
    - Apriori
    - Partition
    - Eclat
    - FP-Growth
- As regras de Associação têm como premissa básica encontrar elementos que implicam na presença de outros elementos em uma mesma transação, ou seja, encontrar relacionamentos ou padrões frequentes entre conjuntos de dados. O termo transação indica quais itens foram consultados em uma determinada operação de consulta. 
- **Análise de Cesta de Compra**
    - Técnica muito utilizada para descobrir padrões de compras
    - Permite identificar associações/relações entre os itens que os clientes compram
     - Caso 'cerveja e fralda': Uma grande rede identificou uma associação nas compras de cerveja e fralda
- **Aplicações**
   -  Melhoria na posição dos produtos
    - Propaganda Direcionada
    - Oferta de cupons
    - Entender o comportamento de cliente
    - Sequência de navegação em sites
    - Sistemas de recomendação
    - Previsão de falhas em telecom
    - Comportamento de usuários
    - Sequência de eventos climáticos
    - Associação de pragas com determinadas culturas
- **Vantagens**
    - Regras de associação são mais simples matematicamente e fáceis de explicar para leigos
    - **Não-supervisionado: requer menos preparação**
    - Ótimo ponto de partida em alguns casos na exploração dos dados
    
## Conteitos

- **Transação** - Operação realizada que gerou um registro de dados, como compras, e devem possuir um Identificador único. 
- **Item** - Elemento que pode fazer parte uma transação, como produtos, páginas de um site, filmes assistidos, etc. 
- **Conjunto de Itens - Itemset** - Coleção de um ou mais itens.

## Exemplo 

**Itens**: 

{'Apple','Corn', 'Dill', 'Eggs', 'Ice cream', 'Kidney Beans', 'Milk','Nutmeg', 'Onion', 'Unicorn', 'Yogurt'}

**transações**

| ID | Apple |Corn |Dill |Eggs |Ice Cream |Kidney Beans |Mil |Nitmeg |Onion |Unicorn |Yogurt|
|---|---|---|---|---|---|---|---|---|---|---|---|
|0 |0 |0 |0 |1 |0 |1 |1 |1 |1 |0 |1 |
|1 |0 |0 |1 |1 |0 |1 |0 |1 |1 |0 |1 |
|2 |1 |0 |0 |1 |0 |1 |1 |0 |0 |0 |0 |
|3 |0 |1 |0 |0 |0 |1 |1 |0 |0 |1 |1 |
|3 |4 |1 |0 |1 |1 |1 |0 |0 |1 |0 |0 |

**itemset 01**
{'Eggs', 'Kidney Beans'}

**itemset 02**
{'Apple', 'Eggs', 'Milk'}


## Support Count - Frequência
- Frequência da ocorrência de um itemset
- Exemplos: 
    - freq({'Apple','Eggs','Milk'}) = 1
    - freq({'Eggs','Kidney Beans'}) = 4
    
## Suport do Itemset
- Fração das transações que contém um itemset
- Exemplos: 
    - freq({'Apple','Eggs','Milk'}) = 1/5
    - freq({'Eggs','Kidney Beans'}) = 4/5
    
## Conjunto Frequênte
- Itemset cujo suporte é o maior ou igual a um limiar definido

# Regras de Associação
    
- Implicação da forma $X \rightarrow Y$ em que X e Y são conjunto de itens frequentes e $X \cup Y = {}$
    - **Implicação significa co-ocorrência, e não causalidade**
- X é o antecedente e Y é o consequente
    - X e Y podem conter vários itens
- {'Eggs'} $\rightarrow$ {'Kidney Beans'}
- {'Eggs', 'Kidney Beans'} $\rightarrow$ {'Onion'}

## Suporte 


- **Qual a probabilidade de uma transação conter o item A e o item B simultaneamente?**
- Fração das Transações que contém X e Y
- Suporte(X $\rightarrow$ Y) = suporte(X $ \cup $ Y) = $\frac{freq(X \cup Y)}{ T}$
- Ex. {'Eggs','Kidney Beans'} → {'Onion'}
    - suporte = freq({'Eggs','Kidney Beans','Onion'}) / 5 = $\frac{3}{5}$
    
## Confiança

- **Entre as transações que contêm A, quantas também contêm B?**
- Frequência de itens em Y que aparecem nas transações que contém X.
- conf($X \rightarrow Y$) = P(X $\mid$ Y) = $\frac{freq(X\cup  Y)}{frec(X)}$
- ex. {'Eggs','Kidney Beans'} → {'Onion'}
     - confiança = $\frac{ freq({'Eggs','Kidney Beans','Onion'})}{freq({'Eggs','Kidney Beans'}) }$ = $\frac{3}{5}$
- **Confiança X Suporte** - Valor de confiança alto é suficiente?
    - Uma regra que somente se aplica a poucas transações pode não ser considerada 'boa'
     - Depende do suporte
     
# Estratégias para reduzir tempo computacional

- Reduzir o número de candidatos (M)
- Reduzir o número de transações (N)
- Reduzir o número de comparações (NM)
    - Usar estruturas de dados eficientes para armazenar candidatos ou transações
    - Eliminar a necessidade de cada candidato ser associado a com toda transação
    
# Algoritmo Apriori

- Se um Itemset é frequente, os seus subconjuntos devem ser frequentes
    - Ex. Se {Leite, Fralda, Cerveja} é frequente, todos os subconjuntos desse Itemset com dois itens também o são
- **Em geral o algorit**

## Lift 

- **O quanto a transação conter A aumenta a probabilidade dela conter B também?**
-  Quando seu valor é $< 1$, a associação é negativa
$$\frac{P(B|A)}{P(B)} = \frac{\frac{freq(A U B)}{freq(A)}}{\frac{freq(B)}{|T|}}$$

# ECLAT

- Versão simplificada do Apriori
- Utiliza somente o suporte
- Algoritmo
    1. Definir o Suporte
    2. Extrair o conjunto de itens que tenham o suporte mínimo
    3. Ordenar os dados de acordo com o suporte

# Conclusões

- Cuidado com a complexidade do algoritmo
- Avalie bem as métricas de interesse, pois **nem sempre um suporte alto e uma confiança alta são suficientes**
- Interpretação do especialista no negócio é fundamental
- Padrão é subjetivamente interessante se gera informação nova, mesmo com suporte baixo