 # Aprendizado de Máquina - Machine Learning

- Sub-área da Inteligência Artificial
- Aprendendo com os dados
- Criar modelos para entender os dados
- Utilizar modelos para predizer novos dados

Supervisionada | Não Supervisionada | Reforço |
--- | --- | --- |
Classificação | Associação | ---
Regressão | Associação | ---
--- | Associação | ---
--- | Agrupamento | ---
--- | Detecção de Desvios | ---
--- | Padrões Sequenciais | ---
--- | Sumarização | ---


## Tipos

- **Não-Supervisionado**
    - Objetivo - Analisar automaticamente os dados
    - Necessita análise para determinar o significado dos padrões encontrados
    - Dados não possuem rótulos
    - Objetivo é separar os dados em grupos semelhantes, ou seja, criar rótulos para os dados
- **Supervisionado**
    - Fluxo
        - Fase I - Extração de Características -> Algoritmo de Aprendizagem (com um supervisor) -> Modelo aprendido
        - Fase II - Extração de Características -> Aplicar no Modelo -> Predição
    - Precisa de um **supervisor para rotular cada uma das classes**
    - Dados possuem rótulos/classes
    - Cria um modelo que relaciona as características (features) dos dados a um rótulo (label)
    - O modelo criado pode ser usado para rotular dados desconhecidos (não-rotulados)
    - A meta é generalizar: Criar um modelo genérico que irá ser capaz de prever classes/rótulos de dados novos e desconhecidos
        1. Separar um sub-conjunto dos dados para treinamento
        2. Treine o modelo
        3. Teste o modelo com os dados que sobraram
- **Aprendizagem por Reforço**
    - Aprender com as iterações com o ambiente (causa e efeito)
    - Aprender com sua própria experiência
    - Robô coletando lixo aprendendo a andar em um ambiente
    - Controle automatizado de elevadores
    
## Sub-conjunto de teste
- **Atenção: nunca utilize para teste os mesmos dados usados para treinamento**
-  Sub-conjunto de teste pode estar tendencioso
- **Solução: Validação Cruzada**
    - Separar os dados D em K sub-conjuntos de aproximadamente mesmo tamanho
    - Para cada sub-conjunto D’, utilize os outros D – D’ para treinar o modelo e D’ para testar
    - Faça a média dos K resultados
    - Quantos sub-conjuntos K?
        - Usualmente, os dados são divididos em 10 sub-conjuntos: 10-fold-cross-validation
        
## Validando o modelo de aprendizado

- Ao se gerar um modelo de classificação, espera-se que ele classifique corretamente as entradas desconhecidas. Porém, às vezes na prática o modelo pode classificar equivocadamente
- A **matriz de confusão** condensa os resultados para facilitar a validação do modelo
    - Quatro possíveis resultados
        1. Mensagem é Spam e o modelo a classifica como Spam:
            - **Verdadeiro Positivo (VP)**
        2. Mensagem não é Spam e o modelo a classifica como não Spam:
            - **Falso Positivo (FP)**
        3. Mensagem é Spam e o modelo a classifica como não Spam:
            - **Falso Negativo (FN)**
        4. Mensagem não é Spam e o modelo a classifica como Spam:
            - **Falso Positivo (FP)**
- **Acurácia**:  no geral, o quão frequente o classificador está correto?
    - Acertos / (Acertos + Erros)
        - (VP + VN) / (VP + VN + FP + FN)
- **Precisão:** Daqueles classificados como corretos, quantos realmente são corretos?
    - Acertos Positivos / (Acertos Positivos + ErrosRequer o número pré-definido de clusters
- **Revogação (Recall)**: Das entradas de classe X, quantos foram classificados realmente como X? 
    - Acertos Positivos / (Acertos Positivos + Falsos Negativos)
        - VP / (VP + FN)
- Precisão x Revogação
    - Ideal 100% para ambos
    - Buscar equilíbrio: VP x FP
    - Aumentar o recall tende a “relaxar” o algoritmo e diminuir a precisão
    - Aumentar a “rigidez” do algoritmo tende a aumentar a precisão e diminuir o recall        


##  Aprendizado Supervisionado Algoritmos

### Classificação 

- Descreve ou prevê um atributo especial
- Usamos a Classificação para prever uma fraude, descobrir qual espécia um determinado animal pertence, prever alguma doença. 
- rótulos são categorias discretas
- Atributo a ser analisado é categórico
- Entrada: vetor de características
- Saída: único valor discreto (a “classe”)
        

### Regressão

- Um tipo de classificação, entretanto a classe é numérica. 
- Prevê a altura  de uma pessoa a partir do pose. 
- rótulos são quantidades contínuas
- Atributo a ser analisado é numérico
- Identifica uma curva para os dados
- Usa a curva aprendida para prever saídas de dados desconhecidos
    

### Regras de Associação 

- Buscam encontra a relação entre os dados. 

### Algoritmos

#### KNN – K Vizinhos Mais Próximos

- Requer três coisas:
    - conjunto de treinamento
    - métrica para distância
    - valor de K
- Para classificar um desconhecido
    - calcula a distância aos objetos de treinamento
    - identifica os K mais próximos
    - use a classe da maioria dos K
- Técnica Lazy: não cria modelo explícito
- Caro para classificar
- Valor do K pode influenciar resultado
- Importante escolher boa métrica de distância

- Ex: Você deseja classificar uma pessoa para prever em quem ela irá votar para presidente
    - Você não sabe nada sobre essa pessoa, além do endereço
    - Pelos dados de treinamento, você sabe como outras pessoas ao longo do território nacional irão votar
    - Se você sabe mais detalhes sobre as pessoas além do endereço (idade, sexo, renda, formação, etc), os K vizinhos são calculados com base em todas essas características
    - Se anda como um pato e “fala” como um pato, provavelmente é um pato
    - **K-NN: verifique como os K vizinhos mais próximos da pessoa irão votar**
    
#### Naive Bayes

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
    
#### Support Vector Machine (SVM)

- Funciona para dados em várias dimensões
- Funciona para dados em com separações não-lineares
- Existem algoritmos eficientes para calcular o melhor hiperplano
    - Requer que usuário decida sobre melhores funções e parâmetros
- Dificuldade em tratar valores vazios
- Robusto a ruído
- Alto custo computacional, mas resultados muito bons

#### Árvores de Decisão

- A função de classificação aprendida é representada por uma árvore de decisão
    - Regras **SE-ENTÃO**
- Aplicações: diagnóstico médico, análise de risco de crédito, etc
- Cada nó especifica o teste de algum atributo da instância
- Cada ramo partindo de um nó corresponde a um dos valores possíveis dos atributos
- Começa pela pergunta:
    - Qual atributo deve ser testado na raiz?
        - Cada atributo é testado para avaliar o quão bem classifica sozinho os exemplos de treinamento
    - Processo se repete até que a árvore esteja completa
        - Abordagem gulosa
- **Quando considerar**:
    - Instâncias são descritas por um conjunto fixo de atributos (Ex. temperatura) e seus valores (ex. quente, morno, frio)
    - A classe é discreta com dois (ex. sim ou não), ou mais possibilidades (ex. risco alto, moderado, médio)
- **Características**
    - Simplicidade para compreensão e interpretação
    - Não necessita normalização dos dados
    - Atributos numéricos e categóricos
    - Bom desempenho e robustez
    - Solução ótima é NP-Completo
        - Heurísticas são utilizadas
    - Pode necessitar de mecanismos de poda para generalizar melhor
    
    
## Aprendizado Não-Supervisionado Algoritmos

### Agrupamento 

- Não existe uma classe
- Tem como objetivo **criar grupos** e atribuir as instâncias dos dados estes grupos. 
- Usos: Identificar grupos de clientes para campanhas de marketing, categorizar novas espécies, etc. 
- **Agrupamento Completo** - Cada elemento é adicionado em um único grupo
- **Agrupamento Parcial** - Cada instância pode pertencera mais de um grupo.
- **Modelo Difuso** - Cada elemento pertence a um grupo segundo a uma probabilidade
- **Modelo Hierárquico** - Permite que o grupo tenha subgrupos. 
- Podem agrupar todos os elementos ou deixar elementos sem grupo (ruídos)

### Clustering

- Segmentação: separar grande conjunto de dados em sub-conjuntos com elementos similares
- Compreensão: gerar descrição mais compacta do conjunto de dados

### Algoritmos 

 
#### K-Means

- Baseado na distância Euclidiana
- Os centros dos clusters são calculados pela média aritmética de seus componentes
- **Algoritmo guloso**
    - Comece com centros de clusters arbitrários
    - Encontre o centro do cluster mais próximo para cada item, e atribua o item a esse cluster 
    - Recalcule o centro dos clusters incluindo os novos membros
- **Repete**
    - por um número fixo de vezes, ou
    - até que não tenha mudança nos clusters, ou
    - até que mudanças sejam mínimas na qualidade
- **Características**
    - Requer o número pré-definido de clusters
    - Algoritmo guloso com pontos iniciais aleatórios
    - Muito simples
    - Complexidade O(NK) por iteração, onde N é o número de atributos e K o número de clusters
    - Fronteiras lineares
    
#### DBScan

- Baseado na densidade dos pontos
    - quantidade de pontos em uma área
- Ponto núcleo: existe pelo menos um número específico de pontos (MinPts) próximos
- Ponto de fronteira: não é um núcleo, mas está na vizinhança de um
- Ponto de ruído: não é núcleo nem de fronteira

