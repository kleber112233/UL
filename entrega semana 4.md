# Especificação Completa — Expressões Regulares

*Identificadores*
```regex
[a-zA-Z_][a-zA-Z0-9_]*
```

*Números inteiros*
```regex
[0-9]+
```

*Booleanos*
```regex
true|false
```

*Strings*
```regex
"([^"]|.)*"
```

*Palavras-chave*
```regex
int|bool|if|else|loop|for|to|out|fim
```

*Operadores*
```regex
==|!=|<=|>=|&&||||+|-|*|/|%|=|<|>|!
```

*Delimitadores*
```regex
(|)|,|[|]
```

*Comentários*
```regex
//[^n]*
```

```regex
/*([^*]|*+[^*/])**+/
```

*Espaços em branco*
```regex
[ trn]+
```


---


## Análise de ambiguidades e regras de resolução

*Ambiguidades Identificadas*

- **Identificadores vs Palavras-chave**: Como as palavras-chave seguem o mesmo padrão dos identificadores, pode ocorrer sobreposição.
- **Operadores compostos vs operadores simples**: `==` vs `=`, `<=` vs `<`, `&&` vs `&`.

*Regras de Resolução*

1. **Palavras-chave têm precedência sobre identificadores**: ao reconhecer um identificador, primeiro verifica-se se ele está na lista de palavras-chave.
2. **Operadores compostos têm prioridade sobre os simples**: o analisador léxico deve verificar os símbolos mais longos primeiro.
3. **Maior comprimento, maior prioridade**: tokens mais longos devem ser reconhecidos antes dos curtos para evitar cortes indevidos.
4. **Ignorar espaços e comentários antes de identificar tokens significativos**: esses elementos são descartados no processo.

Essas regras garantem uma análise léxica previsível e livre de ambiguidade nas expressões regulares usadas.


---


# Estratégia para tratamento de erros léxicos

*Tipos de erros comuns*
- **Caracteres inválidos**: como `@`, `$`, `~`, que não fazem parte do alfabeto da linguagem.
- **Strings não terminadas**: ex: `"isso é uma string sem fim`
- **Números malformados**: ex: `123abc`

*Estratégia de tratamento*

- **Detecção imediata**: ao encontrar um caractere inválido, o analisador lança um erro imediatamente com a linha correspondente.
- **Mensagens explicativas**: cada erro léxico é acompanhado de uma mensagem clara explicando o problema.
- **Recuperação opcional**: a execução pode ser interrompida ou continuar dependendo do modo de compilação (rígido ou tolerante).
- **Registro de erros múltiplos**: possível implementação de lista de erros acumulados para apresentar ao usuário de uma só vez.


---


# Primeiros esboços de mensagens de erro para usuários

- **Caractere inválido:**  
  `Erro léxico na linha 3: Caractere inválido '@'.`

- **Identificador malformado:**  
  `Erro léxico na linha 7: Identificador não pode começar com número. '9valor' inválido.`

- **String não terminada:**  
  `Erro léxico na linha 12: String não finalizada. Esperado aspas de fechamento.`

- **Comentário de bloco não fechado:**  
  `Erro léxico na linha 15: Comentário de bloco não terminado. Fim esperado com '*/'.`

- **Número malformado:**  
  `Erro léxico na linha 9: Número inválido. Encontrado '123abc'. Esperado apenas dígitos.`
