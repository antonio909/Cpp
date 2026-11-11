# Operações Básicas

## 1. Introdução

As operações básicas são fundamentais para desenvolver programas em C++.

Elas permitem realizar cálculos matemáticos, comparar valores, combinar condições, modificar variáveis e manipular informações.

C++ oferece diferentes categorias de operadores:

- Operadores aritméticos.
- Operadores de atribuição.
- Operadores relacionais.
- Operadores lógicos.
- Operadores de incremento e decremento.
- Operadores bit a bit.
- Operadores condicionais.

Neste capítulo, vamos estudar cada categoria, entender como funciona e aprender a utilizá-la em programas reais.

## 2. O que são operadores?

Um operador é um símbolo ou conjunto de símbolos utilizado para realizar uma operação sobre um ou mais valores.

Os valores utilizados pelos operadores são chamados de **operandos**.

Exemplo:

```cpp
int resultado = 10 + 5;
```

Nesse exemplo:

- `10` é o primeiro operando.
- `5` é o segundo operando.
- `+` é o operador de adição.
- `resultado` recebe o valor calculado.

Resultado:

```text
15
```

Os operadores podem trabalhar com diferentes tipos de dados, dependendo das regras da linguagem.

## 3. Operadores Aritméticos

Os operadores aritméticos são utilizados para realizar operações matemáticas.

C++ possui operadores para adição, subtração, multiplicação, divisão e resto da divisão.

### 3.1 Adição (+)

O operador `+` realiza a soma de dois valores.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    int numero2 = 5;

    int resultado = numero1 + numero2;

    std::cout << "Soma: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Soma: 15
```

Também podemos utilizar o operador diretamente:

```cpp
int resultado = 20 + 30;
```

### 3.2 Subtração (-)

O operador `-` realiza a subtração entre dois valores.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero1 = 20;
    int numero2 = 8;

    int resultado = numero1 - numero2;

    std::cout << "Subtracao: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Subtracao: 12
```

### 3.3 Multiplicação (*)

O operador `*` realiza a multiplicação de dois valores.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero1 = 7;
    int numero2 = 4;

    int resultado = numero1 * numero2;

    std::cout << "Multiplicacao: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Multiplicacao: 28
```

### 3.4 Divisão (/)

O operador `/` realiza a divisão entre dois valores.

Exemplo:

```cpp
#include <iostream>

int main() {
    double numero1 = 20;
    double numero2 = 4;

    double resultado = numero1 / numero2;

    std::cout << "Divisao: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Divisao: 5
```

#### Divisão inteira

Quando dois operandos são inteiros, a divisão inteira descarta a parte fracionária do resultado.

Exemplo:

```cpp
#include <iostream>

int main() {
    int resultado = 10 / 3;

    std::cout << resultado << '\n';

    return 0;
}
```

Resultado:

```text
3
```

Isso acontece porque ambos os operandos são do tipo `int`.

Para obter um resultado decimal, podemos utilizar `double`:

```cpp
double resultado = 10.0 / 3.0;
```

Resultado aproximado:

```text
3.33333
```

Também podemos converter um dos operandos:

```cpp
int numero1 = 10;
int numero2 = 3;

double resultado = static_cast<double>(numero1) / numero2;
```

#### Divisão por zero

A divisão inteira por zero possui comportamento indefinido em C++.

Na divisão de ponto flutuante, os resultados seguem as regras do formato numérico e da implementação, podendo envolver infinito ou NaN.

Por isso, em operações que podem receber zero como divisor, devemos realizar uma verificação:

```cpp
#include <iostream>

int main() {
    double numero1 = 10;
    double numero2 = 0;

    if (numero2 != 0) {
        std::cout << numero1 / numero2 << '\n';
    } else {
        std::cout << "Divisao por zero nao permitida.\n";
    }

    return 0;
}
```

### 3.5 Módulo ou Resto da Divisão (%)

O operador `%` retorna o resto de uma divisão inteira.

Exemplo:

```cpp
#include <iostream>

int main() {
    int resultado = 10 % 3;

    std::cout << "Resto: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Resto: 1
```

Explicação:

```text
10 / 3 = 3
3 * 3 = 9
10 - 9 = 1
```

Portanto, o resto da divisão é `1`.

O operador `%` trabalha com tipos inteiros. Não pode ser utilizado diretamente com `float` ou `double`.

#### Verificando se um número é par ou ímpar

O operador `%` é bastante utilizado para verificar se um número é par ou ímpar.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    if (numero % 2 == 0) {
        std::cout << "Numero par\n";
    } else {
        std::cout << "Numero impar\n";
    }

    return 0;
}
```

Resultado:

```text
Numero par
```

Um número é par quando o resto da divisão por 2 é igual a zero.

## 4. Operadores de Atribuição

Os operadores de atribuição são utilizados para armazenar ou modificar valores em variáveis.

O operador básico de atribuição é `=`.

### 4.1 Atribuição simples (=)

O operador `=` atribui um valor a uma variável.

Exemplo:

```cpp
int idade = 20;
```

Nesse exemplo, o valor `20` é armazenado na variável `idade`.

Também podemos modificar o valor posteriormente:

```cpp
int numero = 10;

numero = 25;
```

Agora, `numero` contém o valor `25`.

### 4.2 Atribuição com adição (+=)

O operador `+=` adiciona um valor à variável e armazena o resultado nela.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    numero += 5;

    std::cout << numero << '\n';

    return 0;
}
```

Resultado:

```text
15
```

A expressão:

```cpp
numero += 5;
```

equivale a:

```cpp
numero = numero + 5;
```

### 4.3 Atribuição com subtração (-=)

O operador `-=` subtrai um valor da variável.

Exemplo:

```cpp
int numero = 20;

numero -= 5;
```

Resultado:

```text
15
```

Equivale a:

```cpp
numero = numero - 5;
```

### 4.4 Atribuição com multiplicação (*=)

O operador `*=` multiplica o valor da variável.

Exemplo:

```cpp
int numero = 5;

numero *= 4;
```

Resultado:

```text
20
```

Equivale a:

```cpp
numero = numero * 4;
```

### 4.5 Atribuição com divisão (/=)

O operador `/=` divide o valor da variável por outro valor.

Exemplo:

```cpp
double numero = 20;

numero /= 4;
```

Resultado:

```text
5
```

Equivale a:

```cpp
numero = numero / 4;
```

### 4.6 Atribuição com módulo (%=)

O operador `%=` armazena o resto de uma divisão inteira.

Exemplo:

```cpp
int numero = 17;

numero %= 5;
```

Resultado:

```text
2
```

Equivale a:

```cpp
numero = numero % 5;
```

### 4.7 Resumo dos operadores de atribuição

| Operador | Exemplo | Equivalência |
|---|---|---|
| `=` | `x = 10` | Atribuição simples |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |

## 5. Operadores de Incremento e Decremento

Os operadores de incremento e decremento são utilizados para aumentar ou diminuir o valor de uma variável em uma unidade.

### 5.1 Incremento (++)

O operador `++` adiciona 1 ao valor de uma variável.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    numero++;

    std::cout << numero << '\n';

    return 0;
}
```

Resultado:

```text
11
```

A expressão:

```cpp
numero++;
```

equivale a:

```cpp
numero = numero + 1;
```

### 5.2 Decremento (--)

O operador `--` diminui 1 do valor de uma variável.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    numero--;

    std::cout << numero << '\n';

    return 0;
}
```

Resultado:

```text
9
```

A expressão:

```cpp
numero--;
```

equivale a:

```cpp
numero = numero - 1;
```

### 5.3 Pré-incremento (++variavel)

O pré-incremento aumenta o valor da variável antes de produzir o resultado da expressão.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    int resultado = ++numero;

    std::cout << "Numero: " << numero << '\n';
    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Numero: 11
Resultado: 11
```

Primeiro, `numero` passa de 10 para 11. Depois, o valor atualizado é utilizado na expressão.

### 5.4 Pós-incremento (variavel++)

O pós-incremento produz o valor anterior da variável e depois realiza o incremento.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    int resultado = numero++;

    std::cout << "Numero: " << numero << '\n';
    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Numero: 11
Resultado: 10
```

O valor anterior foi utilizado para inicializar `resultado`. Depois, `numero` foi incrementado.

### 5.5 Pré-decremento (--variavel)

O pré-decremento diminui o valor da variável antes de produzir o resultado da expressão.

```cpp
int numero = 10;

int resultado = --numero;
```

Resultado:

```text
numero = 9
resultado = 9
```

### 5.6 Pós-decremento (variavel--)

O pós-decremento produz o valor anterior e depois diminui a variável.

```cpp
int numero = 10;

int resultado = numero--;
```

Resultado:

```text
numero = 9
resultado = 10
```

### 5.7 Resumo de incremento e decremento

| Operador | Descrição |
|---|---|
| `++x` | Incrementa antes de produzir o resultado. |
| `x++` | Produz o valor anterior e depois incrementa. |
| `--x` | Decrementa antes de produzir o resultado. |
| `x--` | Produz o valor anterior e depois decrementa. |

Esses operadores são bastante utilizados em estruturas de repetição, como `for` e `while`.

## 6. Operadores Relacionais

Os operadores relacionais são utilizados para comparar dois valores.

O resultado de uma comparação é um valor booleano:

- `true`: verdadeiro.
- `false`: falso.

Em C++, o tipo `bool` representa valores booleanos.

### 6.1 Igualdade (==)

Verifica se dois valores são iguais.

```cpp
int a = 10;
int b = 10;

bool resultado = (a == b);
```

Resultado:

```text
true
```

### 6.2 Diferença (!=)

Verifica se dois valores são diferentes.

```cpp
int a = 10;
int b = 5;

bool resultado = (a != b);
```

Resultado:

```text
true
```

### 6.3 Maior que (>)

Verifica se o valor da esquerda é maior que o valor da direita.

```cpp
int a = 10;
int b = 5;

bool resultado = (a > b);
```

Resultado:

```text
true
```

### 6.4 Menor que (<)

Verifica se o valor da esquerda é menor que o valor da direita.

```cpp
int a = 5;
int b = 10;

bool resultado = (a < b);
```

Resultado:

```text
true
```

### 6.5 Maior ou igual (>=)

Verifica se um valor é maior ou igual a outro.

```cpp
int a = 10;
int b = 10;

bool resultado = (a >= b);
```

Resultado:

```text
true
```

### 6.6 Menor ou igual (<=)

Verifica se um valor é menor ou igual a outro.

```cpp
int a = 5;
int b = 10;

bool resultado = (a <= b);
```

Resultado:

```text
true
```

### 6.7 Resumo dos operadores relacionais

| Operador | Significado | Exemplo |
|---|---|---|
| `==` | Igual a | `a == b` |
| `!=` | Diferente de | `a != b` |
| `>` | Maior que | `a > b` |
| `<` | Menor que | `a < b` |
| `>=` | Maior ou igual | `a >= b` |
| `<=` | Menor ou igual | `a <= b` |

### Exemplo prático

```cpp
#include <iostream>

int main() {
    int idade = 18;

    if (idade >= 18) {
        std::cout << "Maior de idade\n";
    } else {
        std::cout << "Menor de idade\n";
    }

    return 0;
}
```

Resultado:

```text
Maior de idade
```

## 7. Operadores Lógicos

Os operadores lógicos são utilizados para combinar ou inverter condições booleanas.

C++ possui três operadores lógicos principais:

- AND (`&&`).
- OR (`||`).
- NOT (`!`).

### 7.1 AND lógico (&&)

O operador `&&` retorna `true` somente quando as duas condições são verdadeiras.

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade = 20;
    bool possuiDocumento = true;

    if (idade >= 18 && possuiDocumento) {
        std::cout << "Condicoes atendidas\n";
    }

    return 0;
}
```

Resultado:

```text
Condicoes atendidas
```

Tabela verdade:

| A | B | A && B |
|---|---|---|
| false | false | false |
| false | true | false |
| true | false | false |
| true | true | true |

### 7.2 OR lógico (||)

O operador `||` retorna `true` quando pelo menos uma das condições é verdadeira.

Exemplo:

```cpp
#include <iostream>

int main() {
    bool temIngresso = false;
    bool possuiConvite = true;

    if (temIngresso || possuiConvite) {
        std::cout << "Entrada autorizada\n";
    }

    return 0;
}
```

Resultado:

```text
Entrada autorizada
```

Tabela verdade:

| A | B | A \|\| B |
|---|---|---|
| false | false | false |
| false | true | true |
| true | false | true |
| true | true | true |

### 7.3 NOT lógico (!)

O operador `!` inverte o valor lógico de uma expressão.

Exemplo:

```cpp
#include <iostream>

int main() {
    bool ativo = true;

    std::cout << !ativo << '\n';

    return 0;
}
```

Resultado:

```text
0
```

Por padrão, o `std::cout` representa `false` como `0` e `true` como `1`.

Podemos utilizar `std::boolalpha` para exibir os nomes:

```cpp
#include <iostream>

int main() {
    bool ativo = true;

    std::cout << std::boolalpha;
    std::cout << !ativo << '\n';

    return 0;
}
```

Resultado:

```text
false
```

Tabela verdade:

| A | !A |
|---|---|
| false | true |
| true | false |

### 7.4 Short-circuit evaluation

Os operadores `&&` e `||` utilizam avaliação de curto-circuito.

Isso significa que a segunda expressão pode não ser avaliada quando o resultado já pode ser determinado pela primeira.

No operador `&&`, se a primeira condição for falsa, a segunda não precisa ser avaliada.

Exemplo:

```cpp
if (false && algumaCondicao()) {
    // Não será executado.
}
```

No operador `||`, se a primeira condição for verdadeira, a segunda não precisa ser avaliada.

Exemplo:

```cpp
if (true || algumaCondicao()) {
    // A condição já é verdadeira.
}
```

Esse comportamento pode ser útil para evitar operações desnecessárias e proteger determinadas verificações.

## 8. Operadores Bit a Bit (Bitwise Operators)

Os operadores bit a bit realizam operações diretamente sobre os bits de valores inteiros.

Eles são utilizados em situações como:

- Manipulação de flags.
- Sistemas embarcados.
- Protocolos de comunicação.
- Operações de baixo nível.
- Manipulação de máscaras de bits.

### 8.1 AND bit a bit (&)

Compara os bits dos dois operandos.

O resultado de cada posição será 1 somente quando ambos os bits forem 1.

Exemplo:

```cpp
int a = 6;
int b = 3;

int resultado = a & b;
```

Representação binária:

```text
6 = 0110
3 = 0011
---------
    0010
```

Resultado:

```text
2
```

### 8.2 OR bit a bit (|)

O operador `|` produz 1 quando pelo menos um dos bits correspondentes é 1.

Exemplo:

```cpp
int a = 6;
int b = 3;

int resultado = a | b;
```

Representação binária:

```text
6 = 0110
3 = 0011
---------
    0111
```

Resultado:

```text
7
```

### 8.3 XOR bit a bit (^)

O operador `^` produz 1 quando os bits correspondentes são diferentes.

Exemplo:

```cpp
int a = 6;
int b = 3;

int resultado = a ^ b;
```

Representação binária:

```text
6 = 0110
3 = 0011
---------
    0101
```

Resultado:

```text
5
```

### 8.4 NOT bit a bit (~)

O operador `~` inverte todos os bits do operando.

Exemplo:

```cpp
unsigned int numero = 5;

unsigned int resultado = ~numero;
```

O resultado depende da quantidade de bits do tipo utilizado.

Para um tipo inteiro sem sinal de N bits, o resultado corresponde à inversão dos N bits.

### 8.5 Deslocamento à esquerda (<<)

O operador `<<` desloca os bits para a esquerda.

Exemplo:

```cpp
unsigned int numero = 5;

unsigned int resultado = numero << 1;
```

Representação simplificada:

```text
5 = 0101
    1010 = 10
```

Resultado:

```text
10
```

### 8.6 Deslocamento à direita (>>)

O operador `>>` desloca os bits para a direita.

Exemplo:

```cpp
unsigned int numero = 8;

unsigned int resultado = numero >> 1;
```

Representação:

```text
8 = 1000
    0100 = 4
```

Resultado:

```text
4
```

> **Atenção:** deslocamentos de bits possuem regras específicas em C++. A quantidade de deslocamento precisa ser válida e os efeitos dependem do tipo e da representação utilizada. Evite deslocamentos inválidos ou valores que provoquem overflow.

### 8.7 Resumo dos operadores bit a bit

| Operador | Nome | Descrição |
|---|---|---|
| `&` | AND bit a bit | AND entre bits correspondentes. |
| `|` | OR bit a bit | OR entre bits correspondentes. |
| `^` | XOR bit a bit | XOR entre bits correspondentes. |
| `~` | NOT bit a bit | Inverte os bits. |
| `<<` | Shift left | Desloca bits à esquerda. |
| `>>` | Shift right | Desloca bits à direita. |

### Diferença entre operadores lógicos e bit a bit

É importante não confundir:

| Operador | Categoria | Funcionamento |
|---|---|---|
| `&&` | Lógico | Combina condições booleanas. |
| `||` | Lógico | Combina condições booleanas. |
| `!` | Lógico | Inverte um valor lógico. |
| `&` | Bit a bit | Opera sobre bits. |
| `|` | Bit a bit | Opera sobre bits. |
| `^` | Bit a bit | Opera sobre bits. |
| `~` | Bit a bit | Inverte bits. |

Exemplo:

```cpp
bool a = true;
bool b = false;

bool resultado = a && b;
```

Nesse caso, estamos realizando uma operação lógica, não uma operação bit a bit.

## 9. Operador Condicional (Ternário)

O operador ternário `?:` permite escolher entre duas expressões com base em uma condição.

Sua estrutura é:

```cpp
condicao ? valor_se_verdadeiro : valor_se_falso;
```

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade = 20;

    std::string resultado =
        (idade >= 18) ? "Maior de idade" : "Menor de idade";

    std::cout << resultado << '\n';

    return 0;
}
```

Resultado:

```text
Maior de idade
```

O operador ternário pode ser utilizado como uma alternativa compacta para algumas estruturas `if/else`.

### Comparação com if/else

Utilizando `if/else`:

```cpp
int numero = 10;
int resultado;

if (numero > 0) {
    resultado = 1;
} else {
    resultado = 0;
}
```

Utilizando o operador ternário:

```cpp
int numero = 10;

int resultado = (numero > 0) ? 1 : 0;
```

Ambos os exemplos produzem o mesmo resultado.

## 10. Precedência dos Operadores

A precedência determina a ordem em que os operadores são avaliados em uma expressão.

Exemplo:

```cpp
int resultado = 10 + 5 * 2;
```

Resultado:

```text
20
```

Isso acontece porque a multiplicação possui precedência maior que a adição.

A expressão é interpretada como:

```cpp
int resultado = 10 + (5 * 2);
```

### 10.1 Tabela simplificada de precedência

A tabela abaixo apresenta grupos de operadores em ordem geral, do maior para o menor nível de precedência.

| Precedência | Operadores | Descrição |
|---|---|---|
| 1 | `++`, `--`, `!`, `~`, `+`, `-` (unários) | Operadores unários |
| 2 | `*`, `/`, `%` | Multiplicação, divisão e módulo |
| 3 | `+`, `-` | Adição e subtração |
| 4 | `<<`, `>>` | Deslocamento de bits |
| 5 | `<`, `<=`, `>`, `>=` | Comparações relacionais |
| 6 | `==`, `!=` | Igualdade e diferença |
| 7 | `&` | AND bit a bit |
| 8 | `^` | XOR bit a bit |
| 9 | `|` | OR bit a bit |
| 10 | `&&` | AND lógico |
| 11 | `||` | OR lógico |
| 12 | `?:` | Operador condicional |
| 13 | `=`, `+=`, `-=`, `*=`, `/=`, `%=` | Atribuição |
| 14 | `,` | Operador vírgula |

> Essa tabela é simplificada. C++ possui uma tabela completa de precedência e associatividade, incluindo operadores adicionais.

### 10.2 Utilizando parênteses

Podemos utilizar parênteses para deixar a ordem de avaliação explícita.

Exemplo:

```cpp
int resultado = (10 + 5) * 2;
```

Resultado:

```text
30
```

Outro exemplo:

```cpp
int resultado = 10 + (5 * 2);
```

Resultado:

```text
20
```

Os parênteses ajudam a tornar expressões complexas mais claras e evitam interpretações equivocadas.

## 11. Associatividade dos Operadores

Associatividade determina como operadores de mesma precedência são agrupados quando aparecem em sequência.

Por exemplo:

```cpp
int resultado = 20 - 5 - 3;
```

O operador de subtração possui associatividade da esquerda para a direita.

Portanto, a expressão equivale a:

```cpp
int resultado = (20 - 5) - 3;
```

Resultado:

```text
12
```

Já os operadores de atribuição possuem associatividade da direita para a esquerda.

Exemplo:

```cpp
int a, b, c;

a = b = c = 10;
```

A expressão é agrupada como:

```cpp
a = (b = (c = 10));
```

Assim, as três variáveis recebem o valor `10`.

## 12. Operadores e Conversão de Tipos

Durante operações, C++ pode realizar conversões de tipos automaticamente.

Esse processo é conhecido como conversão implícita.

Exemplo:

```cpp
int numeroInteiro = 10;
double numeroDecimal = 2.5;

double resultado = numeroInteiro + numeroDecimal;
```

Resultado:

```text
12.5
```

Nesse exemplo, o valor inteiro é convertido para `double` durante a operação.

Também podemos realizar conversões explícitas:

```cpp
int numero = 10;

double resultado = static_cast<double>(numero) / 3;
```

Resultado aproximado:

```text
3.33333
```

O uso de `static_cast` permite indicar claramente a conversão desejada.

## 13. Exemplo Prático — Calculadora Básica

Agora vamos reunir vários operadores em um único programa.

O objetivo será criar uma calculadora que realiza operações matemáticas.

```cpp
#include <iostream>

int main() {
    double numero1;
    double numero2;

    std::cout << "Digite o primeiro numero: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo numero: ";
    std::cin >> numero2;

    std::cout << "\n--- Resultados ---\n";

    std::cout << "Soma: "
              << numero1 + numero2 << '\n';

    std::cout << "Subtracao: "
              << numero1 - numero2 << '\n';

    std::cout << "Multiplicacao: "
              << numero1 * numero2 << '\n';

    if (numero2 != 0) {
        std::cout << "Divisao: "
                  << numero1 / numero2 << '\n';
    } else {
        std::cout << "Divisao: nao permitida\n";
    }

    return 0;
}
```

Possível execução:

```text
Digite o primeiro numero: 20
Digite o segundo numero: 5

--- Resultados ---
Soma: 25
Subtracao: 15
Multiplicacao: 100
Divisao: 4
```

## 14. Boas Práticas ao Utilizar Operadores

Algumas práticas ajudam a escrever códigos mais claros e seguros:

1. Utilize parênteses quando uma expressão puder gerar dúvidas.
2. Evite expressões excessivamente complexas.
3. Verifique divisões por zero.
4. Utilize os tipos de dados adequados.
5. Tenha cuidado com operações entre tipos diferentes.
6. Evite modificar uma variável várias vezes na mesma expressão.
7. Prefira expressões claras em vez de códigos excessivamente compactos.
8. Diferencie operadores lógicos de operadores bit a bit.
9. Entenda a precedência antes de combinar muitos operadores.
10. Utilize `static_cast` quando uma conversão explícita tornar o código mais claro.

## 15. Exercícios Práticos

### Exercício 1 — Operações aritméticas

Crie um programa que receba dois números inteiros e apresente:

- Soma.
- Subtração.
- Multiplicação.
- Divisão inteira.
- Resto da divisão.

### Exercício 2 — Par ou ímpar

Crie um programa que solicite um número inteiro e informe se ele é par ou ímpar.

Utilize o operador `%`.

### Exercício 3 — Maior número

Solicite dois números e utilize operadores relacionais para descobrir qual é o maior.

### Exercício 4 — Operadores lógicos

Crie um programa que receba a idade e verifique se ela está dentro de um intervalo definido.

Utilize `&&` e operadores relacionais.

### Exercício 5 — Incremento e decremento

Crie uma variável inteira com valor inicial 10.

Depois:

1. Utilize pré-incremento.
2. Exiba o resultado.
3. Utilize pós-incremento.
4. Exiba o resultado.
5. Repita o processo com decremento.

### Exercício 6 — Operador ternário

Crie um programa que receba um número e informe se ele é positivo ou não positivo utilizando o operador ternário.

### Exercício 7 — Operações bit a bit

Declare dois números inteiros sem sinal e experimente os operadores:

- `&`
- `|`
- `^`
- `~`
- `<<`
- `>>`

Apresente os resultados.

### Exercício 8 — Calculadora completa

Desenvolva uma calculadora que permita ao usuário escolher entre:

- Adição.
- Subtração.
- Multiplicação.
- Divisão.
- Resto da divisão para números inteiros.

O programa deve verificar se a operação escolhida é válida e evitar divisões por zero.

## 16. Resumo

Neste capítulo, estudamos os principais operadores disponíveis em C++.

| Categoria | Operadores | Finalidade |
|---|---|---|
| Aritméticos | `+`, `-`, `*`, `/`, `%` | Realizar cálculos matemáticos. |
| Atribuição | `=`, `+=`, `-=`, `*=`, `/=`, `%=` | Atribuir e modificar valores. |
| Incremento e decremento | `++`, `--` | Aumentar ou diminuir valores. |
| Relacionais | `==`, `!=`, `>`, `<`, `>=`, `<=` | Comparar valores. |
| Lógicos | `&&`, `||`, `!` | Combinar condições. |
| Bit a bit | `&`, `|`, `^`, `~`, `<<`, `>>` | Manipular bits. |
| Condicional | `?:` | Escolher entre duas expressões. |

Também aprendemos conceitos importantes como:

- Operandos.
- Precedência.
- Associatividade.
- Short-circuit evaluation.
- Conversão de tipos.
- Divisão inteira e divisão decimal.

Os operadores são utilizados praticamente em todos os programas C++. Dominar seu funcionamento é essencial para avançar para estruturas de controle, funções, arrays, ponteiros e outros conceitos da linguagem.

## 17. Referências

- [cppreference — Operators](https://en.cppreference.com/w/cpp/language/expressions)
- [cppreference — Arithmetic Operators](https://en.cppreference.com/w/cpp/language/operator_arithmetic)
- [cppreference — Assignment Operators](https://en.cppreference.com/w/cpp/language/operator_assignment)
- [cppreference — Logical Operators](https://en.cppreference.com/w/cpp/language/operator_logical)
- [cppreference — Bitwise Operators](https://en.cppreference.com/w/cpp/language/operator_arithmetic)
- [LearnCpp — Operators](https://www.learncpp.com/)
- [C++ Reference](https://en.cppreference.com/w/)
