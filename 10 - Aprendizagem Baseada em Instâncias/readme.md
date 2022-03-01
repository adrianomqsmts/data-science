# Resumo

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

# Aprendizagem Baseada em Instância - ABI

- Métodos de aprendizagem baseados em instâncias assumem que as instâncias podem ser representadas como pontos em um espaço Euclidiano
    - Vetores de Características ou Atributo
- Têm  a  característica  de armazenar todas as instâncias de treinamento, processo que provoca o efeito colateral de tais algoritmos exigirem, em muitos domínios de conhecimento, um considerável espaço em  memória  que,  nem  sempre,  está  disponível
    - A aprendizagem consiste somente em armazenar os exemplos de treinamento (vetor de atributos ou características, valor do conceito alvo ou classe)
    - Uma desvantagem é o alto custo para classificação.Toda computação ocorre no momento da classificação. Aumenta com a quantidade de exemplo de treinamento. 
- Os métodos de aprendizagem baseados em instâncias são métodos não paramétricos.
    - **Métodos não paramétricos**: podem ser usados com distribuições arbitrárias e sem a suposição de que a forma das densidades são conhecidas
- No final teremos um **conjunto de distâncias** (medida de similaridade) entre a instância de teste $x_t$ e todos as instâncias de treinamento $x_1, x_2, . . ., x_n$
- **Classificação** - Pegamos a instância de treinamento cuja distância seja a menor e verificamos a classe associada a esta instância

# K-Nearest Neighbor - KNN 


- [Machine Learning na prática com o algoritmo KNN em Python](https://minerandodados.com.br/machine-learning-na-pratica-knn-python/)
- [Aprendizagem de Máquina](http://www.ppgia.pucpr.br/~alekoe/AM/2012/6-kNN-AM-2012.pdf)
- [Aprendizado Baseado em Instâncias Subsidiado por Conjuntos Locais](https://www.cc.faccamp.br/Dissertacoes/SandroVieiraGoncalves.pdf)
- **É um algoritmo que pode ser usado tanto para classificação como regressão**. 
- O algoritmos ele **não constrói um modelo**, ele faz somente o cálculo de distância.
    - Por conta dessa característica, ele é considerado um método do tipo preguiçoso (lazy).
    - Métodos baseados em instâncias simplesmente armazena os exemplos de treinados
    -  Os dados são descartados após a criação do modelo.
    - A generalização/previsão é feita somente quando uma nova instância precisa ser classificada
- Objetivo - Classificar $x_t$ atribuindo a ele o rótulo representado mais frequentemente dentre as $k$ amostras mais próximas e utilizando um esquema de votação.
    - **É determinar a qual grupo uma determinada amostra vai pertencer com base nas amostras vizinhas**. 
- Faz o cálculo da distancia do novo elemento entre todos os elementos para classificá-lo
    - O parâmetro K define quantos elementos devem ser considerados na vizinhança
    
  ![](figuras/KNN.png)
  
- **AS VARIÁVEIS DEVEM ESTAR NA MESMA ESCALA**
- Revisão
    - Naive Bayes - Gera uma tabela de probabilidades
    - Árvore de Decisões - Gera um árvore com caminhos condicionais
    - Algoritmos baseados em regras - Gera várias geras IFs
    - KNN - Realiza cálculos entre as distancias dos vizinhos
    
## Cálculo da distância

- Distância Euclidianda - DE
    1. Subtração de cada posição do vetor
    2. Agora pegamos o resultado de cada operação e elevamos ao quadrado.
    3. Depois somamos esses resultados.
    4. E por último tiramos a raiz quadrada do valor anterior.
    5. Quanto menor esse valor mais próximo os elementos estão.
    
    $$E(x,y) = \sqrt{ \sum_{i=0}^{n}{{(x_i - y_i)}^2}}$$
    
## Normalização e Padronização

- Usados para deixar as variáveis na mesma escala

- Normalização 
    - $x = \frac{x - min(x)}{max(x) - min(x)}$
- Padronização
    - $x = \frac{x - mean(x)}{std(x)}$
    
## Características

- Simples e poderoso
- Indicado quando o relacionamento entre as características é complexo
- Valor de K-pequeno
    - Dados com ruídos podem prejudicar
- Valor de K-grande
    - Pode causar overfitting
- Lento para fazer as previsões
- Outras distâncias
    - Coeficiente de Pearson
    - índice de Tanimoto
    - City Block
