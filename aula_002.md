
# What is C++?

## 1. O que é C++?

C++ é uma linguagem de programação de propósito geral, compilada, estaticamente tipada e multiparadigma. Foi desenvolvida por **Bjarne Stroustrup** no início da década de 1980 como uma extensão da linguagem C.

C++ permite desenvolver programas eficientes, controlar recursos do computador e criar aplicações de diferentes complexidades.

É considerada uma linguagem de alto desempenho porque oferece recursos que permitem ao programador controlar memória, processamento e estruturas de dados com bastante flexibilidade.

## 2. Principais características do C++

### 2.1. Linguagem de propósito geral

C++ pode ser utilizada em diferentes áreas da computação, não estando limitada a um único tipo de aplicação.

Exemplos:

- Desenvolvimento de jogos.
- Sistemas operacionais.
- Aplicações desktop.
- Sistemas embarcados.
- Navegadores.
- Motores gráficos.
- Aplicações científicas.
- Sistemas financeiros.

### 2.2. Linguagem compilada

C++ utiliza um compilador para transformar o código-fonte em código executável.

O processo geralmente envolve:

1. Escrita do código-fonte.
2. Pré-processamento.
3. Compilação.
4. Montagem.
5. Ligação (linking).
6. Geração do executável.

Exemplo:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!\n";

    return 0;
}
```

Compilação utilizando GCC:

```bash
g++ main.cpp -o programa
```

Execução no Windows:

```powershell
.\programa.exe
```

### 2.3. Tipagem estática

C++ possui tipagem estática. Isso significa que os tipos das variáveis são determinados durante a compilação.

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade = 20;
    double altura = 1.75;
    char inicial = 'A';
    bool ativo = true;

    std::cout << idade << '\n';
    std::cout << altura << '\n';
    std::cout << inicial << '\n';
    std::cout << ativo << '\n';

    return 0;
}
```

Cada variável possui um tipo específico, que determina quais valores pode representar e quais operações são permitidas.

### 2.4. Programação procedural

C++ permite organizar programas utilizando funções e procedimentos.

Exemplo:

```cpp
#include <iostream>

int somar(int a, int b) {
    return a + b;
}

int main() {
    int resultado = somar(10, 20);

    std::cout << resultado;

    return 0;
}
```

A função `somar()` recebe dois números e retorna o resultado da adição.

### 2.5. Programação orientada a objetos (OOP)

C++ oferece suporte à programação orientada a objetos.

Os principais conceitos são:

- Classes.
- Objetos.
- Encapsulamento.
- Herança.
- Polimorfismo.
- Abstração.

Exemplo:

```cpp
#include <iostream>
#include <string>

class Carro {
public:
    std::string modelo;

    void acelerar() {
        std::cout << modelo << " está acelerando!\n";
    }
};

int main() {
    Carro meuCarro;

    meuCarro.modelo = "Ferrari";
    meuCarro.acelerar();

    return 0;
}
```

Nesse exemplo:

- `Carro` é uma classe.
- `meuCarro` é um objeto.
- `modelo` é um atributo.
- `acelerar()` é um método.

### 2.6. Programação genérica

C++ possui templates, que permitem criar funções e classes capazes de trabalhar com diferentes tipos de dados.

Exemplo:

```cpp
#include <iostream>

template <typename T>
T maior(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    std::cout << maior(10, 20) << '\n';
    std::cout << maior(3.5, 2.5) << '\n';

    return 0;
}
```

A função `maior()` pode trabalhar com diferentes tipos, desde que eles ofereçam as operações necessárias.

### 2.7. Gerenciamento de memória

C++ permite controlar diretamente a alocação e a liberação de memória.

Exemplo com alocação dinâmica:

```cpp
#include <iostream>

int main() {
    int* numero = new int(100);

    std::cout << *numero << '\n';

    delete numero;

    return 0;
}
```

Entretanto, em C++ moderno, recomenda-se utilizar recursos como `std::unique_ptr`, `std::shared_ptr` e contêineres da STL sempre que apropriado.

## 3. Onde C++ é utilizado?

### 3.1. Desenvolvimento de jogos

Utilizada em motores de jogos, como Unreal Engine, e em sistemas de alto desempenho.

### 3.2. Sistemas operacionais

Utilizada em componentes de sistemas e softwares que precisam de controle de recursos.

### 3.3. Computação gráfica

Utilizada em renderizadores, motores gráficos e aplicações 3D.

### 3.4. Sistemas embarcados

Utilizada em dispositivos eletrônicos, equipamentos e sistemas que possuem recursos limitados.

## 4. Vantagens do C++

- Alto desempenho.
- Controle detalhado de recursos.
- Suporte a múltiplos paradigmas.
- Grande quantidade de bibliotecas.
- Portabilidade entre diferentes sistemas.
- Utilização em projetos de grande escala.
- Compatibilidade com grande parte do ecossistema C.

## 5. Desvantagens do C++

- Sintaxe relativamente complexa.
- Gerenciamento de memória exige atenção.
- Compilação pode ser demorada em projetos grandes.
- Alguns erros podem ser difíceis de identificar.
- Comportamento indefinido (Undefined Behavior) pode causar problemas difíceis de diagnosticar.

## 6. Exemplo prático

Programa simples que calcula a soma de dois números:

```cpp
#include <iostream>

int main() {
    int numero1;
    int numero2;

    std::cout << "Digite o primeiro número: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo número: ";
    std::cin >> numero2;

    int resultado = numero1 + numero2;

    std::cout << "Resultado: " << resultado << '\n';

    return 0;
}
```

### Saída esperada

```text
Digite o primeiro número: 10
Digite o segundo número: 20
Resultado: 30
```

## 7. Resumo

C++ é uma linguagem de programação multiparadigma, compilada e de alto desempenho. Seus recursos permitem desenvolver desde pequenos programas até sistemas complexos.

Seus principais fundamentos incluem:

- Sintaxe e estrutura de programas.
- Variáveis e tipos de dados.
- Funções.
- Ponteiros e referências.
- Classes e objetos.
- Templates.
- Biblioteca padrão (STL).
- Gerenciamento de memória.
- Concorrência e programação avançada.

## 8. Referências

- [ISO C++](https://isocpp.org/)
- [cppreference — C++](https://en.cppreference.com/w/)
- [LearnCpp](https://www.learncpp.com/)
- [Roadmap.sh — C++](https://roadmap.sh/cpp)
