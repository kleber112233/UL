# Cronograma do Projeto — UL (Sujeito a mudança)

## Semana 0 — Preparação e Escolha da Linguagem 
- Definição do nome da linguagem (UL)
- Escolha da ferramenta de implementação (Java)
- Tipo e paradigma definidos
- Redação da visão geral e objetivos

---

## Semana 1 — Especificação Conceitual
- Definir escopo inicial da linguagem (funcionalidades mínimas)
- Esboçar gramática base (BNF ou EBNF)
- Definir tokens e regras léxicas
- Documentar sintaxe e exemplos iniciais
- Início do *Diário de Desenvolvimento*

---

## Semana 2 — Analisador Léxico
- Criar analisador léxico (manual ou com ANTLR)
- Testar reconhecimento de tokens básicos (variáveis, números, operadores, palavras-chave)
- Implementar mensagens de erro léxico
- Ajustar gramática conforme necessário

---

## Semana 3 — Analisador Sintático (Parser) — Parte 1
- Implementar parser para expressões aritméticas e lógicas
- Gerar Árvore de Sintaxe Abstrata (AST) para expressões simples
- Criar casos de teste iniciais para validar parsing

---

## Semana 4 — Analisador Sintático (Parser) — Parte 2
- Adicionar suporte a estruturas de controle (`if`, `while`)
- Implementar parsing de blocos de código
- Tratar erros sintáticos com mensagens amigáveis

---

## Semana 5 — Interpretador Básico
- Implementar execução de AST para expressões aritméticas/lógicas e controle de fluxo
- Adicionar suporte a variáveis e atribuições
- Testar execução de programas simples

---

## Semana 6 — Recursos Adicionais
- Implementar laço `for`
- Adicionar escopo básico para variáveis
- Suporte a operações com strings simples
- Atualizar gramática e testes

---

## Semana 7 — Tratamento de Erros e Análise Semântica
- Melhorar mensagens de erro léxico/sintático/semântico
- Implementar checagem de tipos básica
- Testar casos de erro e comportamentos inesperados

---

## Semana 8 — Testes e Refino
- Criar conjunto de programas exemplo para demonstrar recursos
- Otimizar o interpretador para melhor desempenho
- Refatorar código para clareza e organização

---

## Semana 9 — Documentação Final
- Criar manual da linguagem (sintaxe, exemplos, uso)
- Atualizar README no GitHub
- Finalizar o *Diário de Desenvolvimento*
- Revisar código e comentários

---

## Semana 10 — Entrega e Apresentação
- Preparar apresentação final (slides, exemplos)
- Demonstrar execução de programas na UL
- Entregar código-fonte, documentação e relatórios
