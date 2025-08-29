
#  Análise Formal da Linguagem UL

## 1. Primeira versão da gramática formal da linguagem

```ebnf
Programa         → Declaracao* EOF ;
Declaracao       → "int" IDENT "=" expressao
                 | "bool" IDENT "=" expressao
                 | stmt ;

stmt             → expr ";"
                 | ifStmt
                 | whileStmt
                 | printStmt ;

ifStmt           → "if" "(" expressao ")" bloco ("else" bloco)? "fim" ;
whileStmt        → "loop" "(" expressao ")" bloco "fim" ;
printStmt        → "out" "(" expressao ")" ;

bloco            → "bloco" declaracao* ;
expressao        → logico_or ;

logico_or        → logico_and ( "||" logico_and )* ;
logico_and       → igualdade ( "&&" igualdade )* ;
igualdade        → comparacao ( ("==" | "!=") comparacao )* ;
comparacao       → termo ( (">" | ">=" | "<" | "<=") termo )* ;
termo            → fator ( ("+" | "-") fator )* ;
fator            → unario ( ("*" | "/" | "%") unario )* ;
unario           → ( "!" | "-" ) unario | primario ;
primario         → INT_LITERAL | BOOL_LITERAL | STRING_LITERAL | IDENT
                 | "(" expressao ")" ;
```

---

## 2. Classificação na hierarquia de Chomsky

>  **Tipo 2 – Livre de Contexto**

###  Justificativa:
- Produções seguem o formato A → α (não há múltiplos não-terminais à esquerda).
- Sem dependências contextuais.
- Suporta estruturas aninhadas como blocos e condicionais `if ... fim`.
- Não é Tipo 3 pois permite aninhamento.
- Pode ser reconhecida por autômatos de pilha.

###  Não é:
- Tipo 3 (Regular): Não suporta nesting (ex: `Se ... Se ... Fim`).
- Tipo 1 (Sensível ao contexto): Não possui regras αAβ → αγβ.
- Tipo 0 (Irrestrita): Possui estrutura bem definida e restrita.

---

## 3. Derivações para construtos importantes

###  Exemplo de programa válido:

```
int x = 10
int y = 5

if (x > y)[
    out("x é maior")
    if (y > 2)[
        out("y também é relevante")
    ]
fim
]

loop (x < 15)[
    x = x + 1
    out(x)
]
fim
```

### Derivação parcial:

```
Programa
→ Declaracao*
→ int x = 10
→ int y = 5
→ if ( x > y ) bloco
→ bloco → out("x é maior")
→ if ( y > 2 ) bloco
→ bloco → out("y também é relevante")
→ fim
→ fim
→ loop ( x < 15 ) bloco
→ bloco → x = x + 1
→ bloco → out(x)
→ fim
```

---

## 4. Análise de Ambiguidades

###  Problema: Dangling Else (a qual "if" o "else" pertence?)

```
if condicao1
    if condicao2
        comando1
else
    comando2
fim
```

**Solução:** Sempre associar o `else` ao `if` mais próximo **não pareado**.

---

###  Precedência de operadores:

1. `()` Parênteses
2. `!` Negação
3. `*`, `/`, `%` Multiplicação e divisão
4. `+`, `-` Adição e subtração
5. `==`, `!=`, `<`, `>`, `<=`, `>=` Comparações
6. `&&` E lógico
7. `||` OU lógico

###  Associatividade:

- Aritméticos e lógicos: associativos à esquerda.
- Comparações: não associativos (erro se encadeados).

