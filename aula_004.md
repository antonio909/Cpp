
# C vs C++ — Diferenças entre C e C++

## 1. Introdução

C e C++ são linguagens de programação muito importantes na história da computação. Embora compartilhem algumas características e tenham uma sintaxe semelhante, existem diferenças significativas entre elas.

A linguagem C foi desenvolvida por Dennis Ritchie nos laboratórios Bell, entre 1969 e 1973.

C++ foi desenvolvida por Bjarne Stroustrup no início da década de 1980, inicialmente como uma extensão da linguagem C.

O objetivo do C++ era adicionar novos recursos à linguagem C, especialmente suporte à programação orientada a objetos, mantendo características importantes de desempenho e controle de recursos.

Atualmente, C e C++ são linguagens independentes, com padrões e regras próprias.

## 2. O que é C?

C é uma linguagem de programação de propósito geral, procedural, compilada e estaticamente tipada.

É conhecida por oferecer controle sobre recursos de baixo nível, eficiência e portabilidade.

C é amplamente utilizada em:

- Sistemas operacionais.
- Sistemas embarcados.
- Drivers de dispositivos.
- Sistemas de controle.
- Bibliotecas de software.
- Desenvolvimento de compiladores.
- Programação de baixo nível.

### Exemplo de programa em C

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");

    return 0;
}
```

### Explicação

- `#include <stdio.h>` inclui a biblioteca padrão de entrada e saída.
- `int main()` define a função principal.
- `printf()` exibe uma mensagem no terminal.
- `return 0` indica que o programa terminou com sucesso.

## 3. O que é C++?

C++ é uma linguagem de programação de propósito geral, compilada, estaticamente tipada e multiparadigma.

Ela permite utilizar programação procedural, orientada a objetos e genérica.

C++ oferece recursos adicionais em relação ao C, como:

- Classes e objetos.
- Herança.
- Polimorfismo.
- Encapsulamento.
- Templates.
- Sobrecarga de funções.
- Sobrecarga de operadores.
- Exceções.
- Referências.
- Biblioteca padrão com contêineres e algoritmos.

### Exemplo de programa em C++

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!\n";

    return 0;
}
```

### Explicação

- `#include <iostream>` disponibiliza recursos de entrada e saída.
- `int main()` define a função principal.
- `std::cout` envia informações para a saída padrão.
- `return 0` indica que o programa terminou com sucesso.

## 4. Principais diferenças entre C e C++

Embora compartilhem uma sintaxe semelhante, C e C++ possuem diferentes recursos e filosofias de programação.

| Característica | C | C++ |
|---|---|---|
| Paradigma principal | Procedural | Multiparadigma |
| Tipagem | Estática | Estática |
| Classes | Não possui | Possui |
| Objetos | Não possui classes nativas | Possui |
| Herança | Não possui | Possui |
| Polimorfismo orientado a objetos | Não possui nativamente | Possui |
| Encapsulamento | Não possui classes | Possui |
| Templates | Não possui | Possui |
| Sobrecarga de funções | Não | Sim |
| Sobrecarga de operadores | Não | Sim |
| Referências | Não possui referências da linguagem C++ | Possui |
| Exceções | Não possui sistema nativo de exceções C++ | Possui |
| STL | Não possui | Possui biblioteca padrão de contêineres e algoritmos |
| Gerenciamento de memória | Manual | Manual e recursos de gerenciamento automático |
| Compatibilidade entre códigos | Não se aplica | Compatibilidade parcial com C |

**Importante:** C++ não é simplesmente uma versão mais recente de C. São linguagens diferentes, embora compartilhem muitas características.

## 5. Diferença entre programação procedural e orientada a objetos

Uma das diferenças mais conhecidas entre C e C++ está nos paradigmas de programação.

### 5.1. Programação procedural em C

Na programação procedural, o programa é organizado principalmente por funções que executam tarefas específicas.

Exemplo:

```c
#include <stdio.h>

struct Pessoa {
    char nome[50];
    int idade;
};

void apresentar(struct Pessoa pessoa) {
    printf("Nome: %s\n", pessoa.nome);
    printf("Idade: %d\n", pessoa.idade);
}

int main() {
    struct Pessoa pessoa = {"Carlos", 20};

    apresentar(pessoa);

    return 0;
}
```

Nesse exemplo:

- `struct Pessoa` agrupa dados relacionados.
- `apresentar()` é uma função independente.
- A função recebe a estrutura como argumento.

### 5.2. Programação orientada a objetos em C++

C++ permite agrupar dados e funções dentro de classes.

Exemplo:

```cpp
#include <iostream>
#include <string>

class Pessoa {
public:
    std::string nome;
    int idade;

    void apresentar() {
        std::cout << "Nome: " << nome << '\n';
        std::cout << "Idade: " << idade << '\n';
    }
};

int main() {
    Pessoa pessoa;

    pessoa.nome = "Carlos";
    pessoa.idade = 20;

    pessoa.apresentar();

    return 0;
}
```

Nesse exemplo:

- `class Pessoa` define uma classe.
- `nome` e `idade` são atributos.
- `apresentar()` é um método.
- `pessoa` é um objeto.

**Observação:** C também permite organizar dados e funções de maneira semelhante por meio de estruturas e funções, mas não possui classes e os mecanismos nativos de orientação a objetos de C++.

## 6. Diferença entre entrada e saída de dados

C e C++ utilizam mecanismos diferentes para realizar operações de entrada e saída.

### 6.1. Entrada e saída em C

C utiliza principalmente as funções `printf()` e `scanf()`.

Exemplo:

```c
#include <stdio.h>

int main() {
    int idade;

    printf("Digite sua idade: ");

    scanf("%d", &idade);

    printf("Sua idade: %d\n", idade);

    return 0;
}
```

### Explicação

- `printf()` exibe informações.
- `scanf()` recebe informações.
- `%d` representa um número inteiro.
- `&idade` fornece o endereço da variável para que `scanf()` possa armazenar o valor.

### 6.2. Entrada e saída em C++

C++ utiliza principalmente `std::cout` e `std::cin`.

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade;

    std::cout << "Digite sua idade: ";

    std::cin >> idade;

    std::cout << "Sua idade: " << idade << '\n';

    return 0;
}
```

### Explicação

- `std::cout` realiza a saída de dados.
- `std::cin` realiza a entrada de dados.
- `<<` é o operador de inserção.
- `>>` é o operador de extração.

## 7. Diferença entre gerenciamento de memória

As duas linguagens permitem trabalhar com memória dinâmica, mas possuem mecanismos diferentes.

### 7.1. Alocação dinâmica em C

C utiliza funções como:

- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

Exemplo:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* numero = malloc(sizeof(int));

    if (numero == NULL) {
        return 1;
    }

    *numero = 100;

    printf("%d\n", *numero);

    free(numero);

    return 0;
}
```

### Explicação

- `malloc()` reserva memória dinamicamente.
- `sizeof(int)` informa o tamanho necessário para um inteiro.
- `numero` recebe o endereço da memória alocada.
- `free()` libera a memória reservada.
- A verificação de `NULL` verifica se a alocação falhou.

### 7.2. Alocação dinâmica em C++

C++ oferece `new` e `delete`, além de mecanismos modernos de gerenciamento automático.

Exemplo:

```cpp
#include <iostream>

int main() {
    int* numero = new int(100);

    std::cout << *numero << '\n';

    delete numero;

    return 0;
}
```

### 7.3. Smart pointers em C++

C++ moderno disponibiliza ponteiros inteligentes para ajudar a gerenciar recursos automaticamente.

Exemplo:

```cpp
#include <iostream>
#include <memory>

int main() {
    std::unique_ptr<int> numero =
        std::make_unique<int>(100);

    std::cout << *numero << '\n';

    return 0;
}
```

O `std::unique_ptr` libera automaticamente o objeto quando deixa de existir.

## 8. Diferença entre funções

C não permite sobrecarga de funções nativamente.

Isso significa que não podemos declarar várias funções com o mesmo nome apenas alterando os tipos dos parâmetros.

### Exemplo em C

```c
#include <stdio.h>

int somarInteiros(int a, int b) {
    return a + b;
}

double somarDecimais(double a, double b) {
    return a + b;
}

int main() {
    printf("%d\n", somarInteiros(10, 20));
    printf("%.2f\n", somarDecimais(2.5, 3.5));

    return 0;
}
```

### Exemplo em C++

C++ permite declarar funções com o mesmo nome, desde que suas listas de parâmetros sejam diferentes.

```cpp
#include <iostream>

int somar(int a, int b) {
    return a + b;
}

double somar(double a, double b) {
    return a + b;
}

int main() {
    std::cout << somar(10, 20) << '\n';
    std::cout << somar(2.5, 3.5) << '\n';

    return 0;
}
```

Esse recurso é chamado de **Function Overloading** (sobrecarga de funções).

## 9. Diferença entre bibliotecas

C e C++ possuem bibliotecas padrão diferentes.

### Bibliotecas comuns de C

| Biblioteca | Finalidade |
|---|---|
| `stdio.h` | Entrada e saída |
| `stdlib.h` | Funções gerais e alocação de memória |
| `string.h` | Manipulação de strings |
| `math.h` | Operações matemáticas |
| `time.h` | Manipulação de tempo |
| `stdbool.h` | Tipo booleano em C99 e posteriores |

### Bibliotecas comuns de C++

| Biblioteca | Finalidade |
|---|---|
| `iostream` | Entrada e saída |
| `string` | Manipulação de strings |
| `vector` | Vetores dinâmicos |
| `array` | Arrays de tamanho fixo |
| `algorithm` | Algoritmos |
| `map` | Estruturas de chave e valor |
| `memory` | Gerenciamento de memória |
| `filesystem` | Manipulação de arquivos e diretórios |

## 10. Compatibilidade entre C e C++

C++ mantém compatibilidade com muitas construções de C, mas não é totalmente compatível com a linguagem.

Existem códigos C válidos que não são aceitos como C++ válido.

### Exemplo de código válido em C

```c
#include <stdlib.h>

int main() {
    int* numeros = malloc(5 * sizeof(int));

    if (numeros == NULL) {
        return 1;
    }

    free(numeros);

    return 0;
}
```

Em C++, `malloc()` retorna `void*`, que não é convertido implicitamente para um ponteiro de outro tipo.

Por isso, o código precisa ser adaptado para C++:

```cpp
#include <cstdlib>

int main() {
    int* numeros = new int[5];

    delete[] numeros;

    return 0;
}
```

Em C++ moderno, normalmente é preferível utilizar `std::vector<int>` para esse tipo de situação.

### Exemplo com std::vector

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numeros(5);

    for (int numero : numeros) {
        std::cout << numero << '\n';
    }

    return 0;
}
```

O vetor gerencia automaticamente sua memória.

## 11. Quando utilizar C?

C é uma boa escolha em projetos que exigem simplicidade, controle de baixo nível e integração com ambientes que utilizam a linguagem C.

Exemplos:

- Desenvolvimento de sistemas embarcados.
- Drivers de dispositivos.
- Componentes de sistemas operacionais.
- Microcontroladores.
- Bibliotecas de baixo nível.
- Sistemas com requisitos específicos de portabilidade.

## 12. Quando utilizar C++?

C++ é uma boa escolha em projetos que precisam combinar desempenho com recursos avançados de organização e reutilização de código.

Exemplos:

- Desenvolvimento de jogos.
- Motores gráficos.
- Aplicações científicas.
- Sistemas financeiros.
- Aplicações desktop.
- Simuladores.
- Sistemas de alto desempenho.
- Aplicações que utilizam programação orientada a objetos.

## 13. Qual linguagem aprender primeiro?

A escolha depende dos seus objetivos.

| Objetivo | Linguagem recomendada |
|---|---|
| Aprender programação de baixo nível | C |
| Aprender programação procedural | C ou C++ |
| Desenvolvimento de jogos | C++ |
| Desenvolvimento de sistemas embarcados | C ou C++ |
| Aprender orientação a objetos | C++ |
| Desenvolvimento de motores gráficos | C++ |
| Trabalhar com bibliotecas de baixo nível | C ou C++ |

As duas linguagens são excelentes para aprender conceitos fundamentais da computação.

## 14. Exercício prático

Crie dois programas que realizem a mesma tarefa: calcular a média de três números.

### Versão em C

```c
#include <stdio.h>

int main() {
    float nota1, nota2, nota3;
    float media;

    printf("Digite a primeira nota: ");
    scanf("%f", &nota1);

    printf("Digite a segunda nota: ");
    scanf("%f", &nota2);

    printf("Digite a terceira nota: ");
    scanf("%f", &nota3);

    media = (nota1 + nota2 + nota3) / 3;

    printf("Media: %.2f\n", media);

    return 0;
}
```

### Versão em C++

```cpp
#include <iostream>

int main() {
    double nota1, nota2, nota3;
    double media;

    std::cout << "Digite a primeira nota: ";
    std::cin >> nota1;

    std::cout << "Digite a segunda nota: ";
    std::cin >> nota2;

    std::cout << "Digite a terceira nota: ";
    std::cin >> nota3;

    media = (nota1 + nota2 + nota3) / 3;

    std::cout << "Media: " << media << '\n';

    return 0;
}
```

### Objetivo do exercício

Compare os dois programas e identifique:

1. As diferenças entre `printf()` e `std::cout`.
2. As diferenças entre `scanf()` e `std::cin`.
3. Como cada linguagem declara variáveis.
4. Como cada linguagem organiza a entrada e a saída de dados.
5. Quais recursos tornam C++ diferente de C.

## 15. Resumo

C e C++ são linguagens relacionadas, mas possuem características próprias.

C é uma linguagem procedural, conhecida por sua simplicidade e controle de baixo nível.

C++ é uma linguagem multiparadigma que oferece recursos adicionais, como classes, herança, polimorfismo, templates, exceções e uma biblioteca padrão abrangente.

As duas linguagens continuam sendo utilizadas em sistemas que exigem desempenho, eficiência e controle sobre os recursos computacionais.

## 16. Referências

- [ISO C](https://www.iso.org/standard/74528.html)
- [ISO C++](https://isocpp.org/)
- [cppreference — C](https://en.cppreference.com/w/c)
- [cppreference — C++](https://en.cppreference.com/w/)
- [LearnCpp](https://www.learncpp.com/)
- [Roadmap.sh — C++](https://roadmap.sh/cpp)
