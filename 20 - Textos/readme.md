# Mineração de Texto e Processamento de Linguagem Natural

- É a interpretação ou produção de linguagem humana por computador
- Principais Conceitos:
    - Morfologia: Estrutura das palavras
    - Sintaxe: A forma em que as palavras são utilizadas
    - Semântica: Significado
    - Pragmática: Significado no contexto
    
## Aplicações

- Respostas a perguntas
- Sistemas de Tradução
- Análise de Sentimentos
- Correção Ortográfica
- OCR
- Reconhecimento de Fala
- Sintetização de Fala (Produzir falas)
- Previsão de Digitação
- Classificação de Documentos e Textos
- Resumos

## Conceitos

## Stopwords

Palavras sem valor semântico que podem ser removidas

### Corpus
    Conjunto de dados (texto não estruturado) em linguagem natural

### Annotations

Colocação de anotações no texto, como flexões, dependências, etc.
1. Tokenization: Processo de separar a sentença em suas partes
    - Palavras, pontos, símbolos, etc.
2. Parts-of-Speech Tagging (POS)
  - Adiciona tags a cada token, como por exemplo, se é verbo, substantivo, adjetivo, etc.
3. Lemmatizing (Lemma): Traz a palavra na sua flexão, de modo que possam ser analisadas juntas.
    - Nosso -> meu, é -> ser.
4. Dependency Parsing: Encontra relação entre palavras pais e filhas.