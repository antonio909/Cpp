# Operadores Aritméticos

## 1. Introdução

Os **operadores aritméticos** são símbolos utilizados em C++ para realizar operações matemáticas com valores numéricos e variáveis.

Eles permitem executar cálculos como:

- Adição.
- Subtração.
- Multiplicação.
- Divisão.
- Resto da divisão.
- Incremento.
- Decremento.

Esses operadores são fundamentais para desenvolver calculadoras, sistemas financeiros, jogos, programas científicos e diversas outras aplicações.

### Exemplo básico

```cpp
#include <iostream>

int main() {
    int a = 10;
    int b = 5;

    std::cout << "Adicao: " << a + b << '\n';
    std::cout << "Subtracao: " << a - b << '\n';
    std::cout << "Multiplicacao: " << a * b << '\n';
    std::cout << "Divisao: " << a / b << '\n';

    return 0;
}
```

**Saída:**

```text
Adicao: 15
Subtracao: 5
Multiplicacao: 50
Divisao: 2
```

---

## 2. Tipos de operadores aritméticos

C++ disponibiliza os seguintes operadores aritméticos principais:

| Operador | Nome | Descrição |
|---|---|---|
| `+` | Addition | Realiza adição |
| `-` | Subtraction | Realiza subtração |
| `*` | Multiplication | Realiza multiplicação |
| `/` | Division | Realiza divisão |
| `%` | Modulus | Retorna o resto da divisão |
| `++` | Increment | Incrementa uma variável |
| `--` | Decrement | Decrementa uma variável |

Os operadores `+`, `-`, `*`, `/` e `%` são operadores binários, pois normalmente trabalham com dois operandos.

Os operadores `++` e `--` são unários, pois trabalham com um operando.

---

# 3. Adição (+)

O operador `+` realiza a soma de dois valores.

### Sintaxe

```cpp
valor1 + valor2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    int numero2 = 20;

    int resultado = numero1 + numero2;

    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
Resultado: 30
```

### Adição com números decimais

O operador também pode ser utilizado com tipos como `float` e `double`.

```cpp
#include <iostream>

int main() {
    double numero1 = 10.5;
    double numero2 = 5.2;

    double resultado = numero1 + numero2;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
15.7
```

### Adição de múltiplos valores

É possível utilizar vários operadores de adição na mesma expressão.

```cpp
int resultado = 10 + 20 + 30 + 40;
```

Resultado:

```text
100
```

---

# 4. Subtração (-)

O operador `-` realiza a subtração entre dois valores.

### Sintaxe

```cpp
valor1 - valor2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero1 = 50;
    int numero2 = 20;

    int resultado = numero1 - numero2;

    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
Resultado: 30
```

### Resultado negativo

Uma subtração pode produzir um resultado negativo.

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    int numero2 = 25;

    int resultado = numero1 - numero2;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
-15
```

### Operador de negação

O símbolo `-` também pode ser utilizado como operador unário para inverter o sinal de um valor.

```cpp
int numero = 10;

int resultado = -numero;
```

Resultado:

```text
-10
```

---

# 5. Multiplicação (*)

O operador `*` realiza a multiplicação entre dois valores.

### Sintaxe

```cpp
valor1 * valor2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    int numero2 = 5;

    int resultado = numero1 * numero2;

    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
50
```

### Multiplicação com números decimais

```cpp
#include <iostream>

int main() {
    double preco = 15.50;
    int quantidade = 3;

    double total = preco * quantidade;

    std::cout << "Total: " << total << '\n';

    return 0;
}
```

**Saída:**

```text
Total: 46.5
```

### Aplicação prática

O operador de multiplicação pode ser utilizado para calcular áreas.

```cpp
#include <iostream>

int main() {
    double largura = 5.0;
    double altura = 3.0;

    double area = largura * altura;

    std::cout << "Area: " << area << '\n';

    return 0;
}
```

**Saída:**

```text
Area: 15
```

---

# 6. Divisão (/)

O operador `/` realiza a divisão entre dois valores.

### Sintaxe

```cpp
valor1 / valor2
```

### Exemplo com números inteiros

```cpp
#include <iostream>

int main() {
    int numero1 = 20;
    int numero2 = 5;

    int resultado = numero1 / numero2;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
4
```

## 6.1. Divisão inteira

Quando os dois operandos são inteiros, C++ realiza uma divisão inteira.

A parte fracionária do resultado é descartada, ou seja, o resultado é truncado em direção a zero.

```cpp
#include <iostream>

int main() {
    int resultado = 10 / 3;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
3
```

Outro exemplo:

```cpp
int resultado = 7 / 2;
```

Resultado:

```text
3
```

Isso acontece porque os dois operandos são do tipo `int`.

## 6.2. Divisão com números decimais

Para obter um resultado decimal, pelo menos um dos operandos precisa ser convertido para um tipo de ponto flutuante.

```cpp
#include <iostream>

int main() {
    double resultado = 10.0 / 3.0;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída aproximada:**

```text
3.33333
```

Também é possível utilizar conversão explícita:

```cpp
int a = 10;
int b = 3;

double resultado = static_cast<double>(a) / b;
```

O `static_cast<double>` converte `a` para `double` antes da divisão.

## 6.3. Divisão por zero

A divisão inteira por zero possui comportamento indefinido em C++.

Portanto, é necessário verificar o divisor antes de realizar a operação.

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    int numero2 = 0;

    if (numero2 != 0) {
        std::cout << numero1 / numero2 << '\n';
    } else {
        std::cout << "Erro: divisao por zero!\n";
    }

    return 0;
}
```

**Saída:**

```text
Erro: divisao por zero!
```

---

# 7. Resto da divisão (%)

O operador `%` retorna o resto de uma divisão inteira.

### Sintaxe

```cpp
valor1 % valor2
```

### Exemplo

```cpp
#include <iostream>

int main() {
    int resultado = 10 % 3;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
1
```

Explicação:

```text
10 / 3 = 3
3 * 3 = 9
10 - 9 = 1
```

O resto da divisão é `1`.

## 7.1. Exemplos adicionais

| Expressão | Resultado |
|---|---:|
| `10 % 2` | 0 |
| `10 % 3` | 1 |
| `15 % 4` | 3 |
| `20 % 5` | 0 |
| `17 % 6` | 5 |
| `25 % 7` | 4 |

## 7.2. Verificar números pares e ímpares

O operador `%` é muito utilizado para verificar se um número é par ou ímpar.

Um número é par quando o resto da divisão por `2` é igual a zero.

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

**Saída:**

```text
Numero par
```

## 7.3. Limitação do operador %

O operador `%` é utilizado com tipos inteiros. Ele não aceita diretamente operandos `float` ou `double`.

Para calcular o resto de uma divisão com números de ponto flutuante, existe a função `std::fmod()` da biblioteca `<cmath>`.

```cpp
#include <iostream>
#include <cmath>

int main() {
    double resultado = std::fmod(10.5, 3.0);

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
1.5
```

---

# 8. Incremento (++)

O operador `++` aumenta o valor de uma variável em uma unidade.

### Sintaxe

```cpp
variavel++;
```

ou

```cpp
++variavel;
```

Existem duas formas de incremento:

- Pré-incremento (`++variavel`).
- Pós-incremento (`variavel++`).

## 8.1. Pré-incremento

No pré-incremento, a variável é incrementada antes de o valor da expressão ser utilizado.

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

**Saída:**

```text
Numero: 11
Resultado: 11
```

Funcionamento:

1. A variável começa com valor `10`.
2. O operador `++numero` incrementa a variável.
3. O valor passa a ser `11`.
4. A expressão produz o valor `11`.

## 8.2. Pós-incremento

No pós-incremento, a expressão produz o valor anterior da variável e, em seguida, a variável é incrementada.

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

**Saída:**

```text
Numero: 11
Resultado: 10
```

Funcionamento:

1. A variável começa com valor `10`.
2. A expressão produz o valor antigo, `10`.
3. A variável é incrementada.
4. A variável passa a valer `11`.

## 8.3. Comparação entre pré e pós-incremento

| Operador | Nome | Comportamento |
|---|---|---|
| `++x` | Pré-incremento | Incrementa antes de produzir o valor da expressão |
| `x++` | Pós-incremento | Produz o valor antigo e depois incrementa |

### Exemplo comparativo

```cpp
#include <iostream>

int main() {
    int a = 5;
    int b = 5;

    std::cout << ++a << '\n';
    std::cout << b++ << '\n';

    std::cout << a << '\n';
    std::cout << b << '\n';

    return 0;
}
```

**Saída:**

```text
6
5
6
6
```

---

# 9. Decremento (--)

O operador `--` diminui o valor de uma variável em uma unidade.

### Sintaxe

```cpp
variavel--;
```

ou

```cpp
--variavel;
```

Assim como o incremento, existem duas formas:

- Pré-decremento (`--variavel`).
- Pós-decremento (`variavel--`).

## 9.1. Pré-decremento

No pré-decremento, a variável é decrementada antes de o valor da expressão ser utilizado.

```cpp
#include <iostream>

int main() {
    int numero = 10;

    int resultado = --numero;

    std::cout << "Numero: " << numero << '\n';
    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
Numero: 9
Resultado: 9
```

## 9.2. Pós-decremento

No pós-decremento, a expressão produz o valor antigo da variável e, em seguida, a variável é decrementada.

```cpp
#include <iostream>

int main() {
    int numero = 10;

    int resultado = numero--;

    std::cout << "Numero: " << numero << '\n';
    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
Numero: 9
Resultado: 10
```

## 9.3. Comparação entre pré e pós-decremento

| Operador | Nome | Comportamento |
|---|---|---|
| `--x` | Pré-decremento | Decrementa antes de produzir o valor da expressão |
| `x--` | Pós-decremento | Produz o valor antigo e depois decrementa |

---

# 10. Operadores aritméticos compostos

C++ também permite combinar operações aritméticas com o operador de atribuição.

Esses operadores são conhecidos como **operadores de atribuição composta**.

| Operador | Equivalência |
|---|---|
| `+=` | `x = x + valor` |
| `-=` | `x = x - valor` |
| `*=` | `x = x * valor` |
| `/=` | `x = x / valor` |
| `%=` | `x = x % valor` |

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero = 10;

    numero += 5;
    std::cout << numero << '\n';

    numero -= 3;
    std::cout << numero << '\n';

    numero *= 2;
    std::cout << numero << '\n';

    numero /= 4;
    std::cout << numero << '\n';

    numero %= 3;
    std::cout << numero << '\n';

    return 0;
}
```

**Saída:**

```text
15
12
24
6
0
```

---

# 11. Precedência dos operadores aritméticos

A precedência determina a ordem em que os operadores são avaliados dentro de uma expressão.

Considere:

```cpp
int resultado = 10 + 5 * 2;
```

O resultado será `20`, e não `30`, porque a multiplicação possui precedência maior que a adição.

### Ordem de precedência

| Prioridade | Operadores | Descrição |
|---|---|---|
| Maior | `++`, `--`, `+`, `-` unários | Incremento, decremento e sinais unários |
| Alta | `*`, `/`, `%` | Multiplicação, divisão e resto |
| Menor | `+`, `-` binários | Adição e subtração |

### Exemplo

```cpp
#include <iostream>

int main() {
    int resultado = 10 + 5 * 2;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
20
```

## 11.1. Utilizando parênteses

Os parênteses podem ser utilizados para controlar explicitamente a ordem das operações.

```cpp
int resultado = (10 + 5) * 2;
```

Resultado:

```text
30
```

Comparação:

```cpp
10 + 5 * 2       // 20
(10 + 5) * 2     // 30
```

**Boa prática:** utilize parênteses quando uma expressão puder gerar dúvidas sobre a ordem das operações.

---

# 12. Conversão de tipos em operações aritméticas

Quando diferentes tipos numéricos são utilizados em uma expressão, C++ pode realizar conversões automáticas.

Esse processo é conhecido como conversão aritmética usual (*usual arithmetic conversions*).

### Exemplo

```cpp
#include <iostream>

int main() {
    int numero1 = 10;
    double numero2 = 3.5;

    double resultado = numero1 + numero2;

    std::cout << resultado << '\n';

    return 0;
}
```

**Saída:**

```text
13.5
```

Nesse caso, o valor inteiro é convertido para `double` durante a operação.

### Conversão explícita

Também é possível realizar conversões manualmente utilizando `static_cast`.

```cpp
int numero1 = 10;
int numero2 = 3;

double resultado = static_cast<double>(numero1) / numero2;
```

Resultado aproximado:

```text
3.33333
```

---

# 13. Exemplo prático: Calculadora simples

O exemplo a seguir utiliza os principais operadores aritméticos para construir uma calculadora.

```cpp
#include <iostream>

int main() {
    double numero1;
    double numero2;

    std::cout << "Digite o primeiro numero: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo numero: ";
    std::cin >> numero2;

    std::cout << "\nResultados:\n";

    std::cout << "Adicao: "
              << numero1 + numero2 << '\n';

    std::cout << "Subtracao: "
              << numero1 - numero2 << '\n';

    std::cout << "Multiplicacao: "
              << numero1 * numero2 << '\n';

    if (numero2 != 0) {
        std::cout << "Divisao: "
                  << numero1 / numero2 << '\n';
    } else {
        std::cout << "Divisao: impossivel dividir por zero.\n";
    }

    return 0;
}
```

### Exemplo de execução

```text
Digite o primeiro numero: 20
Digite o segundo numero: 5

Resultados:
Adicao: 25
Subtracao: 15
Multiplicacao: 100
Divisao: 4
```

---

# 14. Exemplo prático: Verificador de par ou ímpar

Este programa utiliza o operador de resto da divisão (`%`) para verificar se um número é par ou ímpar.

```cpp
#include <iostream>

int main() {
    int numero;

    std::cout << "Digite um numero: ";
    std::cin >> numero;

    if (numero % 2 == 0) {
        std::cout << "O numero e par.\n";
    } else {
        std::cout << "O numero e impar.\n";
    }

    return 0;
}
```

---

# 15. Erros comuns

## 15.1. Confundir divisão inteira com divisão decimal

```cpp
int resultado = 10 / 3;
```

Resultado:

```text
3
```

Para obter um resultado decimal:

```cpp
double resultado = 10.0 / 3.0;
```

## 15.2. Dividir por zero

Evite realizar divisões sem verificar se o divisor é diferente de zero.

```cpp
if (divisor != 0) {
    resultado = numero / divisor;
}
```

## 15.3. Utilizar `%` com números decimais

O código abaixo não é válido:

```cpp
double resultado = 10.5 % 3.0;
```

Para números de ponto flutuante, utilize `std::fmod()`.

## 15.4. Confundir pré-incremento com pós-incremento

```cpp
int x = 5;

int a = ++x; // a recebe 6
int b = x++; // b recebe 6; x passa a 7
```

Ao final:

```text
a = 6
b = 6
x = 7
```

## 15.5. Modificar uma variável várias vezes na mesma expressão

Evite expressões complexas que incrementem ou decrementem a mesma variável diversas vezes.

Prefira separar as operações em instruções distintas para deixar o código claro e evitar problemas de sequenciamento.

---

# 16. Boas práticas

- Utilize nomes de variáveis que indiquem o propósito dos valores.
- Utilize `double` quando precisar trabalhar com valores decimais e maior precisão que `float` normalmente oferece.
- Verifique o divisor antes de realizar uma divisão.
- Utilize `static_cast` quando precisar deixar uma conversão explícita.
- Utilize parênteses para deixar expressões complexas mais claras.
- Evite expressões com vários incrementos ou decrementos da mesma variável.
- Lembre-se de que divisão entre inteiros descarta a parte fracionária.
- Utilize `std::fmod()` para calcular o resto com números de ponto flutuante.

---

# 17. Exercícios práticos

## Exercício 1 — Operações básicas

Crie um programa que receba dois números inteiros e apresente:

- Soma.
- Subtração.
- Multiplicação.
- Divisão inteira.

## Exercício 2 — Divisão decimal

Crie um programa que receba dois números e apresente o resultado da divisão com casas decimais.

## Exercício 3 — Par ou ímpar

Solicite um número inteiro e verifique se ele é par ou ímpar utilizando `%`.

## Exercício 4 — Incremento e decremento

Crie uma variável com valor `10` e execute:

1. Pré-incremento.
2. Pós-incremento.
3. Pré-decremento.
4. Pós-decremento.

Apresente os resultados de cada operação.

## Exercício 5 — Calculadora

Desenvolva uma calculadora que permita realizar:

- Adição.
- Subtração.
- Multiplicação.
- Divisão.

O programa deve receber dois números e um operador escolhido pelo usuário.

## Exercício 6 — Média aritmética

Crie um programa que receba três notas e calcule a média aritmética.

Fórmula:

```text
media = (nota1 + nota2 + nota3) / 3
```

## Exercício 7 — Conversão de tempo

Crie um programa que receba uma quantidade de segundos e converta o valor para horas, minutos e segundos.

Dica: utilize os operadores `/` e `%`.

---

# 18. Resumo

Os operadores aritméticos são fundamentais para realizar cálculos em C++.

| Operador | Nome | Exemplo | Resultado |
|---|---|---|---:|
| `+` | Adição | `10 + 5` | 15 |
| `-` | Subtração | `10 - 5` | 5 |
| `*` | Multiplicação | `10 * 5` | 50 |
| `/` | Divisão | `10 / 5` | 2 |
| `%` | Resto | `10 % 3` | 1 |
| `++` | Incremento | `++x` | x + 1 |
| `--` | Decremento | `--x` | x - 1 |

Também é importante compreender:

- A diferença entre divisão inteira e divisão decimal.
- A diferença entre pré-incremento e pós-incremento.
- A diferença entre pré-decremento e pós-decremento.
- A precedência dos operadores.
- As conversões de tipos numéricos.
- Os cuidados necessários ao dividir valores.

---

# 19. Referências

- [cppreference — Arithmetic operators](https://en.cppreference.com/w/cpp/language/operator_arithmetic)
- [cppreference — Usual arithmetic conversions](https://en.cppreference.com/w/cpp/language/usual_arithmetic_conversions)
- [cppreference — std::fmod](https://en.cppreference.com/w/cpp/numeric/math/fmod)
- [LearnCpp — Arithmetic operators](https://www.learncpp.com/)
- [ISO C++](https://isocpp.org/)
