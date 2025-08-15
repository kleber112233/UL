## Visão Geral

*Nome da Linguagem:* UL  
*Ferramenta de Implementação:* Java (utilizando bibliotecas padrão e eventualmente bibliotecas de apoio para análise léxica/sintática, como JavaCC ou ANTLR)  
*Tipo:* Linguagem interpretada, baseada em gramática livre de contexto (CFG)  
*Paradigma:* Imperativo estruturado  
*Finalidade:* Educacional – foco no aprendizado de compiladores e linguagens formais  

### O que faremos
O projeto consiste no desenvolvimento de uma *linguagem livre de contexto* (CFG) com foco educacional, voltada para o aprendizado de lógica de programação e fundamentos de compiladores. A ideia é criar uma linguagem simples, mas expressiva, que permita a escrita de programas contendo *variáveis*, *operações aritméticas e lógicas*, *estruturas de controle* (`if`, `while`, `for`) e *blocos de código*.  

O objetivo principal é fornecer uma base prática para aplicar conceitos de *gramáticas livres de contexto*, *autômatos de pilha* e *análise sintática*, conectando teoria e prática de forma clara.

### O que é
A linguagem permitirá que o usuário escreva programas com sintaxe clara e reduzida, interpretados diretamente por um *parser + interpretador* implementado pela equipe em Java.  
Não se trata de uma linguagem de propósito geral, mas de um ambiente controlado para exercitar:
- Definição de gramáticas (EBNF).
- Implementação de analisadores léxicos e sintáticos.
- Construção de uma Árvore de Sintaxe Abstrata (AST) e execução.

### Breve sobre o MVP
Nesta primeira versão, o foco será:
- Implementar análise léxica para um conjunto reduzido de tokens.
- Implementar parser para a gramática inicial.
- Executar programas básicos (cálculos, condições, laços) via interpretador.
- Garantir mensagens de erro claras (léxico e sintaxe).

### Objetivo Principal
Criar uma linguagem livre de contexto simples e didática que permita a escrita e execução de programas básicos, servindo como ferramenta prática para o estudo de compiladores.

### Objetivos Específicos
- *Facilitar o aprendizado* de gramáticas livres de contexto e análise sintática.
- *Proporcionar prática* na implementação de parsers e interpretadores em Java.
- *Fornecer exemplos claros* de execução para instrução em sala de aula.
- *Estimular o trabalho em equipe* e o aprendizado colaborativo.

### Alinhamento com a matéria
O projeto conecta diretamente os conteúdos de *Compiladores e Linguagens Formais e Autômatos*, especialmente:
- *Análise léxica* (expressões regulares e DFA).
- *Análise sintática* (gramáticas livres de contexto e PDA).
- *Semântica básica* (checagem de tipos e escopos simples).

### Metas Futuras *(não oficiais)*
- Adicionar funções e escopos locais.
- Suportar arrays e strings.
- Implementar análise semântica mais robusta.
- Adicionar geração de código para outra linguagem (ex.: JavaScript).

---

## Público-Alvo Pretendido

A linguagem é destinada a:

- *Estudantes de Computação e áreas afins*  
  Que estejam aprendendo compiladores e teoria de linguagens formais.

- *Professores e instrutores*  
  Para demonstrar conceitos de gramáticas e execução de programas simples.

- *Entusiastas de linguagens de programação*  
  Que desejam entender o funcionamento interno de um interpretador.

### Justificativa da Escolha do Público
Focar em um público acadêmico e instrucional garante que a linguagem seja usada como ferramenta de aprendizado, cumprindo seu papel de ponte entre teoria e prática no estudo de compiladores.
