# Entrega Semana 5 - Projeto Integrador

## Diagramas dos AFDs

### Identificadores
Regex: `[a-zA-Z_][a-zA-Z0-9_]*`

```mermaid
stateDiagram-v2
    [*] --> Start
    Start --> Ident : letra ou "_"
    Ident --> Ident : letra, dígito ou "_"
    Ident --> [*]
```

### Números inteiros
Regex: `[0-9]+`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : dígito
    Q1 --> Q1 : dígito
    Q1 --> [*]
```

### Booleanos
Regex: `true|false`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : 't'
    Q1 --> Q2 : 'r'
    Q2 --> Q3 : 'u'
    Q3 --> Q4 : 'e'
    Q4 --> [*]

    Q0 --> Q5 : 'f'
    Q5 --> Q6 : 'a'
    Q6 --> Q7 : 'l'
    Q7 --> Q8 : 's'
    Q8 --> Q9 : 'e'
    Q9 --> [*]
```

### Strings
Regex: `"([^"]|.)*"`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : '"'
    Q1 --> Q1 : caractere válido
    Q1 --> Q2 : '"'
    Q2 --> [*]
```

### Palavras-chave
Regex: `int|bool|if|else|loop|for|to|out|fim`

Exemplo para `int`:

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : 'i'
    Q1 --> Q2 : 'n'
    Q2 --> Q3 : 't'
    Q3 --> [*]
```

(O mesmo se aplica para as demais palavras-chave.)

### Operadores
Regex: `==|!=|<=|>=|&&||...`

Exemplo para `==`:

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : '='
    Q1 --> Q2 : '='
    Q2 --> [*]
```

### Delimitadores
Regex: `(|)|,|[|]`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : '('
    Q1 --> [*]
```

(Repete-se para cada delimitador.)

### Comentários de linha
Regex: `//[^n]*`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : '/'
    Q1 --> Q2 : '/'
    Q2 --> Q2 : caractere não '\n'
    Q2 --> Q3 : '\n'
    Q3 --> [*]
```

### Espaços em branco
Regex: `[ 	
]+`

```mermaid
stateDiagram-v2
    [*] --> Q0
    Q0 --> Q1 : espaço ou quebra de linha
    Q1 --> Q1 : espaço ou quebra de linha
    Q1 --> [*]
```

---

## Implementação em Java

```java
public class Automato {
    private int estadoAtual;
    private int[][] transicoes;
    private boolean[] finais;

    public Automato(int[][] transicoes, boolean[] finais) {
        this.estadoAtual = 0;
        this.transicoes = transicoes;
        this.finais = finais;
    }

    public boolean processa(String entrada) {
        estadoAtual = 0;
        for (char c : entrada.toCharArray()) {
            int simbolo = mapearSimbolo(c);
            if (simbolo == -1) return false;
            estadoAtual = transicoes[estadoAtual][simbolo];
            if (estadoAtual == -1) return false;
        }
        return finais[estadoAtual];
    }

    private int mapearSimbolo(char c) {
        if (Character.isLetter(c)) return 0;
        if (Character.isDigit(c)) return 1;
        if (c == '_') return 2;
        return -1;
    }
}
```

---



## Testes Unitários

```java
@Test
public void testIdentificador() {
    Automato ident = Automatos.getIdentificador();
    assertTrue(ident.processa("x"));
    assertTrue(ident.processa("variavel1"));
    assertFalse(ident.processa("1abc"));
}
```
Resultados Esperados

Entrada: "x" => Aceito

Entrada: "variavel1" => Aceito 

Entrada: "1abc" => Rejeitado 
---
