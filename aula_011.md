# Operadores Lógicos

## 1. Introdução

Os **operadores lógicos** são utilizados em C++ para combinar, inverter e avaliar expressões booleanas.

Eles permitem que um programa tome decisões com base em uma ou mais condições.

Os operadores lógicos trabalham principalmente com valores booleanos:

- `true` — verdadeiro.
- `false` — falso.

Em C++, os operadores lógicos são fundamentais para estruturas condicionais, como `if`, `else if` e `while`.

### Exemplo básico

```cpp
#include <iostream>

int main() {
    int idade = 20;

    if (idade >= 18 && idade <= 60) {
        std::cout << "Condicao verdadeira!\n";
    }

    return 0;
}
```

**Saída:**

```text
Condicao verdadeira!
```

Nesse exemplo, o programa verifica duas condições:

1. A idade é maior ou igual a 18?
2. A idade é menor ou igual a 60?

O operador `&&` exige que ambas sejam verdadeiras.

---

# 2. Tipos de operadores lógicos

C++ possui três operadores lógicos principais:

| Operador | Nome | Descrição |
|---|---|---|
| `&&` | Logical AND | Retorna verdadeiro se ambas as condições forem verdadeiras |
| `||` | Logical OR | Retorna verdadeiro se pelo menos uma condição for verdadeira |
| `!` | Logical NOT | Inverte o valor lógico de uma expressão |

Esses operadores são utilizados para construir condições mais complexas.

---

# 3. E lógico

O operador `&&` representa o operador lógico AND (E).

Ele retorna `true` somente quando todas as condições avaliadas são verdadeiras.

### Sintaxe

```cpp
condicao1 && condicao2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    int idade = 25;
    bool possuiCarteira = true;

    if (idade >= 18 && possuiCarteira) {
        std::cout << "Pode dirigir.\n";
    } else {
        std::cout << "Nao pode dirigir.\n";
    }

    return 0;
}
```

**Saída:**

```text
Pode dirigir.
```

### Explicação

O programa verifica duas condições:

- `idade >= 18`: verifica se a pessoa possui idade suficiente.
- `possuiCarteira`: verifica se a variável indica que existe uma carteira de habilitação.

Como ambas são verdadeiras, a expressão completa retorna `true`.

## 3.1. Tabela-verdade do AND

| A | B | A && B |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

### Exemplo com diferentes combinações

```cpp
#include <iostream>

int main() {
    bool a = true;
    bool b = false;

    std::cout << std::boolalpha;

    std::cout << (a && true) << '\n';
    std::cout << (a && false) << '\n';
    std::cout << (b && true) << '\n';
    std::cout << (b && false) << '\n';

    return 0;
}
```

**Saída:**

```text
true
false
false
false
```

O manipulador `std::boolalpha` faz com que os valores booleanos sejam exibidos como `true` e `false`, em vez de `1` e `0`.

---

# 4. OU lógico

O operador `||` representa o operador lógico OR (OU).

Ele retorna `true` quando pelo menos uma das condições é verdadeira.

### Sintaxe

```cpp
condicao1 || condicao2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    bool possuiIngresso = false;
    bool possuiConvite = true;

    if (possuiIngresso || possuiConvite) {
        std::cout << "Entrada permitida.\n";
    } else {
        std::cout << "Entrada negada.\n";
    }

    return 0;
}
```

**Saída:**

```text
Entrada permitida.
```

### Explicação

O programa verifica duas condições:

- A pessoa possui ingresso?
- A pessoa possui convite?

Como pelo menos uma delas é verdadeira, a expressão completa retorna `true`.

## 4.1. Tabela-verdade do OR

| A | B | A \|\| B |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

### Exemplo com diferentes combinações

```cpp
#include <iostream>

int main() {
    bool a = true;
    bool b = false;

    std::cout << std::boolalpha;

    std::cout << (a || true) << '\n';
    std::cout << (a || false) << '\n';
    std::cout << (b || true) << '\n';
    std::cout << (b || false) << '\n';

    return 0;
}
```

**Saída:**

```text
true
true
true
false
```

---

# 5. NÃO lógico

O operador `!` representa o operador lógico NOT (NÃO).

Ele inverte o valor lógico de uma expressão:

- `true` passa a ser `false`.
- `false` passa a ser `true`.

### Sintaxe

```cpp
!condicao
```

### Exemplo

```cpp
#include <iostream>

int main() {
    bool estaChovendo = false;

    if (!estaChovendo) {
        std::cout << "Pode sair sem chuva.\n";
    }

    return 0;
}
```

**Saída:**

```text
Pode sair sem chuva.
```

### Explicação

A variável `estaChovendo` possui o valor `false`.

Ao utilizar `!estaChovendo`, o valor é invertido para `true`.

Consequentemente, o bloco do `if` é executado.

## 5.1. Tabela-verdade do NOT

| A | !A |
|---|---|
| `true` | `false` |
| `false` | `true` |

### Exemplo com valores booleanos

```cpp
#include <iostream>

int main() {
    bool a = true;
    bool b = false;

    std::cout << std::boolalpha;

    std::cout << !a << '\n';
    std::cout << !b << '\n';

    return 0;
}
```

**Saída:**

```text
false
true
```

---

# 6. Avaliação de curto-circuito

Uma característica importante dos operadores `&&` e `||` em C++ é a avaliação de curto-circuito (*short-circuit evaluation*).

Isso significa que o programa pode deixar de avaliar a segunda expressão quando o resultado já pode ser determinado pela primeira.

## 6.1. Short-circuit com AND (&&)

No operador `&&`, se a primeira condição for falsa, a segunda não precisa ser avaliada.

Isso acontece porque uma expressão AND somente será verdadeira quando todas as condições forem verdadeiras.

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero = 10;

    if (numero < 5 && numero / 0 > 1) {
        std::cout << "Condicao verdadeira.\n";
    } else {
        std::cout << "Condicao falsa.\n";
    }

    return 0;
}
```

**Saída:**

```text
Condicao falsa.
```

### Explicação

1. O programa verifica `numero < 5`.
2. Como `10 < 5` é falso, o resultado de toda a expressão AND já é conhecido.
3. A segunda expressão não é avaliada.

**Atenção:** a divisão por zero foi utilizada apenas para demonstrar o curto-circuito. Não escreva expressões que dependam desse comportamento para evitar operações inválidas em outras situações.

## 6.2. Short-circuit com OR (||)

No operador `||`, se a primeira condição for verdadeira, a segunda não precisa ser avaliada.

Isso acontece porque uma expressão OR já será verdadeira quando pelo menos uma condição for verdadeira.

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero = 10;

    if (numero > 5 || numero / 0 > 1) {
        std::cout << "Condicao verdadeira.\n";
    }

    return 0;
}
```

**Saída:**

```text
Condicao verdadeira.
```

### Explicação

1. O programa verifica `numero > 5`.
2. Como `10 > 5` é verdadeiro, o resultado da expressão OR já é conhecido.
3. A segunda expressão não é avaliada.

## 6.3. Comparação do curto-circuito

| Operador | Primeira condição | Segunda condição |
|---|---|---|
| `&&` | `false` | Não é avaliada |
| `&&` | `true` | É avaliada |
| `||` | `true` | Não é avaliada |
| `||` | `false` | É avaliada |

O curto-circuito também é importante quando a segunda condição depende de um valor que precisa ser validado primeiro.

### Exemplo prático: evitando acesso inválido

```cpp
#include <iostream>

int main() {
    int numero = 0;

    if (numero != 0 && 100 / numero > 5) {
        std::cout << "Resultado maior que 5.\n";
    } else {
        std::cout << "Condicao nao satisfeita.\n";
    }

    return 0;
}
```

**Saída:**

```text
Condicao nao satisfeita.
```

A primeira condição garante que o divisor não seja zero antes que a segunda expressão seja avaliada.

---

# 7. Operadores lógicos com estruturas condicionais

Os operadores lógicos são frequentemente utilizados com `if`, `else if` e `else`.

## 7.1. Utilizando AND (&&)

```cpp
#include <iostream>

int main() {
    int idade = 22;

    if (idade >= 18 && idade <= 60) {
        std::cout << "Idade dentro do intervalo.\n";
    } else {
        std::cout << "Idade fora do intervalo.\n";
    }

    return 0;
}
```

**Saída:**

```text
Idade dentro do intervalo.
```

## 7.2. Utilizando OR (||)

```cpp
#include <iostream>

int main() {
    int dia = 6;

    if (dia == 6 || dia == 7) {
        std::cout << "Final de semana.\n";
    } else {
        std::cout << "Dia util.\n";
    }

    return 0;
}
```

**Saída:**

```text
Final de semana.
```

## 7.3. Utilizando NOT (!)

```cpp
#include <iostream>

int main() {
    bool usuarioLogado = false;

    if (!usuarioLogado) {
        std::cout << "Usuario nao autenticado.\n";
    }

    return 0;
}
```

**Saída:**

```text
Usuario nao autenticado.
```

---

# 8. Combinando operadores lógicos

É possível combinar os três operadores em uma única expressão.

### Exemplo

```cpp
#include <iostream>

int main() {
    int idade = 25;
    bool possuiIngresso = true;
    bool eventoCancelado = false;

    if (idade >= 18 && possuiIngresso && !eventoCancelado) {
        std::cout << "Acesso permitido.\n";
    } else {
        std::cout << "Acesso negado.\n";
    }

    return 0;
}
```

**Saída:**

```text
Acesso permitido.
```

### Explicação

A expressão verifica três condições:

1. `idade >= 18`: a idade deve ser maior ou igual a 18.
2. `possuiIngresso`: deve possuir ingresso.
3. `!eventoCancelado`: o evento não pode estar cancelado.

Todas as condições precisam ser verdadeiras.

## 8.1. Utilizando parênteses

Os parênteses permitem agrupar condições e deixar explícita a ordem desejada.

```cpp
#include <iostream>

int main() {
    bool possuiIngresso = false;
    bool possuiConvite = true;
    bool eventoDisponivel = true;

    if ((possuiIngresso || possuiConvite) && eventoDisponivel) {
        std::cout << "Entrada permitida.\n";
    } else {
        std::cout << "Entrada negada.\n";
    }

    return 0;
}
```

**Saída:**

```text
Entrada permitida.
```

A expressão significa:

- Possui ingresso OU convite.
- E o evento está disponível.

---

# 9. Precedência dos operadores lógicos

A precedência determina a ordem em que os operadores são avaliados.

Entre os operadores lógicos:

1. `!` — NOT.
2. `&&` — AND.
3. `||` — OR.

### Exemplo

```cpp
bool resultado = true || false && false;
```

A expressão é interpretada como:

```cpp
bool resultado = true || (false && false);
```

Primeiro ocorre o AND:

```text
false && false = false
```

Depois ocorre o OR:

```text
true || false = true
```

Resultado final:

```text
true
```

### Tabela de precedência

| Prioridade | Operador | Descrição |
|---|---|---|
| Maior | `!` | NOT |
| Intermediária | `&&` | AND |
| Menor | `||` | OR |

**Boa prática:** utilize parênteses em expressões lógicas complexas para tornar a intenção mais clara.

---

# 10. Operadores lógicos e valores booleanos

Em C++, o tipo `bool` armazena dois valores:

- `true`.
- `false`.

Entretanto, expressões lógicas também podem utilizar outros tipos numéricos.

Em contextos de conversão para booleano:

- Zero é convertido para `false`.
- Valores diferentes de zero são convertidos para `true`.

### Exemplo

```cpp
#include <iostream>

int main() {
    int a = 10;
    int b = 0;

    std::cout << std::boolalpha;

    std::cout << !a << '\n';
    std::cout << !b << '\n';

    return 0;
}
```

**Saída:**

```text
false
true
```

Isso acontece porque `10` é convertido para `true`, enquanto `0` é convertido para `false`.

O operador `!` inverte esses valores.

---

# 11. Diferença entre operadores lógicos e bitwise

C++ possui operadores lógicos e operadores bitwise (operações em nível de bits).

Embora alguns símbolos sejam parecidos, eles possuem finalidades diferentes.

| Operador lógico | Operador bitwise | Finalidade |
|---|---|---|
| `&&` | `&` | AND lógico ou AND bit a bit |
| `||` | `|` | OR lógico ou OR bit a bit |
| `!` | `~` | NOT lógico ou NOT bit a bit |

### Exemplo com operadores lógicos

```cpp
#include <iostream>

int main() {
    int a = 5;
    int b = 3;

    std::cout << std::boolalpha;
    std::cout << (a > 2 && b < 5) << '\n';

    return 0;
}
```

**Saída:**

```text
true
```

### Exemplo com operadores bitwise

```cpp
#include <iostream>

int main() {
    int a = 5;
    int b = 3;

    std::cout << (a & b) << '\n';

    return 0;
}
```

**Saída:**

```text
1
```

O operador `&` realiza uma operação bit a bit, enquanto `&&` avalia condições lógicas.

---

# 12. Exemplo prático: Sistema de acesso

O exemplo abaixo utiliza operadores lógicos para verificar se um usuário atende às condições de acesso de um sistema fictício.

```cpp
#include <iostream>

int main() {
    bool usuarioAtivo = true;
    bool senhaCorreta = true;
    bool contaBloqueada = false;

    if (usuarioAtivo && senhaCorreta && !contaBloqueada) {
        std::cout << "Acesso autorizado.\n";
    } else {
        std::cout << "Acesso negado.\n";
    }

    return 0;
}
```

**Saída:**

```text
Acesso autorizado.
```

---

# 13. Exemplo prático: Classificação de notas

Este programa verifica se um estudante foi aprovado, considerando uma média mínima e a frequência.

```cpp
#include <iostream>

int main() {
    double nota;
    int frequencia;

    std::cout << "Digite a nota: ";
    std::cin >> nota;

    std::cout << "Digite a frequencia (%): ";
    std::cin >> frequencia;

    if (nota >= 7.0 && frequencia >= 75) {
        std::cout << "Aprovado!\n";
    } else {
        std::cout << "Reprovado.\n";
    }

    return 0;
}
```

**Exemplo de execução:**

```text
Digite a nota: 8.5
Digite a frequencia (%): 90

Aprovado!
```

---

# 14. Erros comuns

## 14.1. Confundir AND (&&) com OR (||)

```cpp
if (idade >= 18 && idade <= 60)
```

As duas condições precisam ser verdadeiras.

Já nesta expressão:

```cpp
if (idade < 18 || idade > 60)
```

Pelo menos uma condição precisa ser verdadeira.

## 14.2. Utilizar um único & no lugar de &&

Incorreto para uma condição lógica comum:

```cpp
if (idade >= 18 & idade <= 60)
```

Forma recomendada:

```cpp
if (idade >= 18 && idade <= 60)
```

O operador `&` realiza AND bit a bit e não possui o mesmo comportamento de curto-circuito de `&&`.

## 14.3. Confundir atribuição com comparação

Incorreto quando a intenção é comparar:

```cpp
if (idade = 18)
```

Correto:

```cpp
if (idade == 18)
```

- `=` realiza atribuição.
- `==` realiza comparação de igualdade.

## 14.4. Esquecer o operador NOT

Considere:

```cpp
if (usuarioLogado)
```

Essa condição será verdadeira quando o usuário estiver logado.

Para verificar o contrário:

```cpp
if (!usuarioLogado)
```

## 14.5. Ignorar a precedência

Expressões complexas podem produzir resultados diferentes do esperado quando os operadores não são agrupados corretamente.

Prefira:

```cpp
if ((idade >= 18 && idade <= 60) || possuiAutorizacao)
```

---

# 15. Boas práticas

- Utilize `&&` quando todas as condições precisarem ser verdadeiras.
- Utilize `||` quando pelo menos uma condição precisar ser verdadeira.
- Utilize `!` para inverter uma condição.
- Prefira expressões booleanas claras e fáceis de entender.
- Utilize parênteses para agrupar condições complexas.
- Aproveite o curto-circuito para validar valores antes de utilizá-los.
- Não confunda operadores lógicos com operadores bitwise.
- Evite expressões muito longas; divida condições complexas em variáveis booleanas quando necessário.

### Exemplo de código organizado

```cpp
#include <iostream>

int main() {
    int idade = 25;
    bool possuiAutorizacao = false;

    bool idadePermitida = idade >= 18 && idade <= 60;
    bool acessoPermitido = idadePermitida || possuiAutorizacao;

    if (acessoPermitido) {
        std::cout << "Acesso permitido.\n";
    } else {
        std::cout << "Acesso negado.\n";
    }

    return 0;
}
```

---

# 16. Exercícios práticos

## Exercício 1 — AND

Crie um programa que receba a idade de uma pessoa e verifique se ela está entre 18 e 30 anos.

Utilize o operador `&&`.

## Exercício 2 — OR

Crie um programa que receba um número e verifique se ele é igual a 10 ou igual a 20.

Utilize o operador `||`.

## Exercício 3 — NOT

Crie uma variável booleana chamada `estaChovendo`.

Utilize o operador `!` para verificar se não está chovendo.

## Exercício 4 — Par ou ímpar e intervalo

Crie um programa que receba um número inteiro e verifique se ele é par e está entre 1 e 100.

Utilize `&&` e `%`.

## Exercício 5 — Sistema de acesso

Crie um programa com três variáveis:

- `usuarioAtivo`.
- `senhaCorreta`.
- `contaBloqueada`.

O acesso somente deve ser permitido quando:

- O usuário estiver ativo.
- A senha estiver correta.
- A conta não estiver bloqueada.

Utilize `&&` e `!`.

## Exercício 6 — Verificação de intervalo

Receba um número e verifique se ele está fora do intervalo entre 10 e 50.

Utilize `||`.

## Exercício 7 — Expressões lógicas

Determine o resultado de cada expressão:

```cpp
true && false
true || false
!true
!false
true && true || false
!(true && false)
```

Explique a ordem de avaliação de cada uma.

---

# 17. Resumo

Os operadores lógicos permitem combinar e inverter condições em C++.

| Operador | Nome | Resultado |
|---|---|---|
| `&&` | AND | Verdadeiro quando ambas as condições são verdadeiras |
| `||` | OR | Verdadeiro quando pelo menos uma condição é verdadeira |
| `!` | NOT | Inverte o valor lógico |

### Tabelas-verdade resumidas

**AND (`&&`)**

| A | B | Resultado |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

**OR (`||`)**

| A | B | Resultado |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

**NOT (`!`)**

| A | Resultado |
|---|---|
| `true` | `false` |
| `false` | `true` |

### Conceitos importantes

- AND exige que todas as condições sejam verdadeiras.
- OR exige que pelo menos uma condição seja verdadeira.
- NOT inverte o valor lógico.
- `&&` e `||` utilizam avaliação de curto-circuito.
- A precedência lógica é `!`, depois `&&` e, por último, `||`.
- Os operadores lógicos são amplamente utilizados em estruturas condicionais e laços de repetição.

---

# 18. Referências

- [cppreference — Logical operators](https://en.cppreference.com/w/cpp/language/operator_logical)
- [cppreference — Boolean type](https://en.cppreference.com/w/cpp/language/types)
- [LearnCpp — Logical operators](https://www.learncpp.com/)
- [ISO C++](https://isocpp.org/)
