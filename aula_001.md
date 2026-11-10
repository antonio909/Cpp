
# Introdução à Linguagem C++

## 1. O que é C++?

C++ é uma linguagem de programação de propósito geral, compilada e de alto desempenho. Foi criada por Bjarne Stroustrup como uma extensão da linguagem C.

Ela permite desenvolver diferentes tipos de aplicações, como:

- Jogos eletrônicos.
- Sistemas operacionais.
- Aplicações desktop.
- Sistemas embarcados.
- Navegadores.
- Softwares de alto desempenho.
- Aplicações científicas.

C++ oferece recursos de programação procedural, orientada a objetos e genérica.

## 2. História da linguagem C++

A linguagem C++ foi desenvolvida por Bjarne Stroustrup no início da década de 1980, nos laboratórios Bell.

Inicialmente, recebeu o nome de **C with Classes**, pois adicionava recursos de orientação a objetos à linguagem C.

Em 1983, passou a ser chamada de C++.

O nome representa o operador de incremento `++` da linguagem C.

### Principais versões

| Versão | Ano | Principais novidades |
|---|---:|---|
| C++98 | 1998 | Primeira padronização oficial |
| C++03 | 2003 | Correções e melhorias |
| C++11 | 2011 | Auto, lambdas, smart pointers e move semantics |
| C++14 | 2014 | Melhorias em templates e lambdas |
| C++17 | 2017 | Structured bindings e filesystem |
| C++20 | 2020 | Concepts, ranges e coroutines |
| C++23 | 2023 | Novas funcionalidades e melhorias |

## 3. Características do C++

### Linguagem compilada

O código C++ precisa passar por um compilador para ser transformado em um programa executável.

Exemplo:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!";

    return 0;
}
```

### Alto desempenho

C++ permite controlar diversos aspectos da execução do programa e do gerenciamento de memória.

### Tipagem estática

Os tipos das variáveis são conhecidos durante a compilação.

```cpp
int idade = 18;
double altura = 1.75;
char inicial = 'A';
bool ativo = true;
```

### Orientação a objetos

C++ permite trabalhar com classes, objetos, herança, encapsulamento e polimorfismo.

```cpp
#include <iostream>
#include <string>

class Pessoa {
public:
    std::string nome;

    void apresentar() {
        std::cout << "Olá, " << nome;
    }
};

int main() {
    Pessoa pessoa;

    pessoa.nome = "Carlos";
    pessoa.apresentar();

    return 0;
}
```

### Programação genérica

C++ utiliza templates para criar códigos que funcionam com diferentes tipos de dados.

```cpp
#include <iostream>

template <typename T>
T somar(T a, T b) {
    return a + b;
}

int main() {
    std::cout << somar(10, 20) << '\n';
    std::cout << somar(2.5, 3.5);

    return 0;
}
```

## 4. C++ versus C

C e C++ são linguagens relacionadas, mas possuem diferenças importantes.

| Característica | C | C++ |
|---|---|---|
| Paradigma | Procedural | Multiparadigma |
| Classes | Não | Sim |
| Herança | Não nativa | Sim |
| Polimorfismo | Não nativo | Sim |
| Templates | Não | Sim |
| STL | Não | Sim |
| Gerenciamento de memória | Manual | Manual e recursos de gerenciamento automático |

## 5. Compiladores C++

Um compilador transforma o código-fonte em código executável.

Principais compiladores:

- GCC (g++).
- Clang.
- Microsoft Visual C++ (MSVC).
- Intel oneAPI DPC++/C++ Compiler.

Exemplo de compilação utilizando GCC:

```bash
g++ main.cpp -o programa
```

Execução no Windows:

```powershell
.\programa.exe
```

## 6. Estrutura básica de um programa C++

Todo programa C++ precisa de uma função principal chamada `main()`.

Exemplo:

```cpp
#include <iostream>

int main() {

    std::cout << "Olá, mundo!";

    return 0;
}
```

### Explicação do código

**`#include <iostream>`**

Inclui a biblioteca responsável pelas operações básicas de entrada e saída.

**`int main()`**

Define a função principal do programa.

**`std::cout`**

Exibe informações no terminal.

**`return 0`**

Indica que o programa terminou com sucesso.

## 7. Entrada e saída de dados

C++ utiliza `cout` para saída e `cin` para entrada de dados.

```cpp
#include <iostream>

int main() {

    int idade;

    std::cout << "Digite sua idade: ";

    std::cin >> idade;

    std::cout << "Sua idade é: " << idade;

    return 0;
}
```

## 8. Variáveis e tipos de dados

Variáveis armazenam informações utilizadas pelo programa.

```cpp
#include <iostream>
#include <string>

int main() {
    int numero = 10;
    float preco = 15.50f;
    double altura = 1.80;
    char letra = 'A';
    bool aprovado = true;
    std::string nome = "Carlos";

    return 0;
}
```

### Principais tipos

| Tipo | Descrição | Exemplo |
|---|---|---|
| `int` | Números inteiros | `10` |
| `float` | Números decimais | `10.5f` |
| `double` | Decimais com maior precisão | `10.555` |
| `char` | Um caractere | `'A'` |
| `bool` | Verdadeiro ou falso | `true` |
| `string` | Texto | `"Olá"` |

## 9. Onde C++ é utilizado?

C++ é utilizado em diversas áreas da tecnologia:

- Desenvolvimento de jogos com Unreal Engine.
- Sistemas operacionais e componentes de sistemas.
- Motores gráficos.
- Aplicações financeiras.
- Sistemas embarcados.
- Computação científica.
- Aplicações de inteligência artificial de alto desempenho.

## 10. Primeiro exercício

Crie um programa que solicite o nome e a idade de uma pessoa e apresente essas informações no terminal.

### Exemplo de solução

```cpp
#include <iostream>
#include <string>

int main() {

    std::string nome;
    int idade;

    std::cout << "Digite seu nome: ";
    std::getline(std::cin, nome);

    std::cout << "Digite sua idade: ";
    std::cin >> idade;

    std::cout << "\nDados cadastrados:\n";
    std::cout << "Nome: " << nome << '\n';
    std::cout << "Idade: " << idade << '\n';

    return 0;
}
```

---

## Referências para estudo

- [Documentação oficial do C++](https://isocpp.org/)
- [cppreference](https://en.cppreference.com/w/)
- [Learn C++](https://www.learncpp.com/)
- [Roadmap C++](https://roadmap.sh/cpp)
