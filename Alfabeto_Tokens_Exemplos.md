# Especificação do Alfabeto


## Definição do Alfabeto

* **Letras**

  ```math
  Σ₁ = { 'A','B',...,'Z','a','b',...,'z' }
  ```

* **Dígitos**

  ```math
  Σ₂ = { '0','1',...,'9' }
  ```

* **Underscore**

  ```math
  Σ₃ = { '_' }
  ```

* **Espaços em branco**

  ```math
  Σ₄ = { ' ', '\t', '\n', '\r' }
  ```

* **Delimitadores**

  ```math
  Σ₅ = { '(', ')', '{', '}', ';', ',' }
  ```

* **Operadores**

  ```math
  Σ₆ = { '+', '-', '*', '/', '%', '!', '=', '<', '>', '&', '|' }
  ```

---

### Alfabeto completo

```math
Σ = Σ₁ ∪ Σ₂ ∪ Σ₃ ∪ Σ₄ ∪ Σ₅ ∪ Σ₆
```


---

# Tokens da Linguagem

## Palavras-chave (KEYWORDS)
- `int`
- `bool`
- `if`
- `else`
- `loop`
- `for`
- `to`
- `out`
- `fim`

## Identificadores (IDENT)
- Exemplos: `x`, `y`, `soma`, `contador`

## Números inteiros (INT_LITERAL)
- Exemplos: `0`, `7`, `2025`

## Booleanos (BOOL_LITERAL)
- `true`
- `false`

## Operadores (OPERATORS)
- Aritméticos: `+`, `-`, `*`, `/`, `%`
- Atribuição e comparação: `=`, `==`, `!=`, `<`, `>`, `<=`, `>=`
- Lógicos: `&&`, `||`, `!`

## Delimitadores (DELIMITERS)
- `(`, `)`, `,`

## Espaços em branco e comentários (IGNORED)
- Espaços: `(espaço)`, `\n` (quebra de linha)
- Comentários: `// comentário`, `/* comentário de bloco */`

## Fim de arquivo (EOF)
- Marca o término do programa

--

# Exemplos concretos de programas válidos na linguagem

int x = 5
int y = 3

if (x > y)
    out(x)
fim
