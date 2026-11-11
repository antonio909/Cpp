
# Why Use C++? — Por que usar C++?

## 1. Por que utilizar C++?

C++ é uma das linguagens de programação mais utilizadas em projetos que exigem alto desempenho, eficiência e controle sobre os recursos do computador.

Ela oferece ferramentas para desenvolver desde pequenos programas até sistemas complexos, como motores de jogos, sistemas operacionais, aplicações científicas e softwares de engenharia.

Uma das principais razões para utilizar C++ é a possibilidade de combinar desempenho, flexibilidade e diferentes paradigmas de programação.

## 2. Alto desempenho (High Performance)

Uma das maiores vantagens do C++ é seu alto desempenho.

Como C++ é uma linguagem compilada, seu código pode ser transformado em instruções executadas diretamente pelo processador, sem depender necessariamente de uma máquina virtual ou interpretador em tempo de execução.

Isso permite criar aplicações que utilizam os recursos do computador de maneira eficiente.

### Exemplo

```cpp
#include <iostream>
#include <chrono>

int main() {
    auto inicio = std::chrono::high_resolution_clock::now();

    long long soma = 0;

    for (int i = 0; i < 1000000; i++) {
        soma += i;
    }

    auto fim = std::chrono::high_resolution_clock::now();

    std::chrono::duration<double> duracao = fim - inicio;

    std::cout << "Resultado: " << soma << '\n';
    std::cout << "Tempo: " << duracao.count() << " segundos\n";

    return 0;
}
```

### Explicação

- `std::chrono` fornece ferramentas para trabalhar com tempo.
- `inicio` registra o instante inicial.
- O `for` executa um milhão de iterações.
- `fim` registra o instante final.
- `duracao` calcula o tempo decorrido.
- `count()` retorna a duração em segundos.

**Importante:** o tempo de execução depende do processador, do compilador, das opções de otimização e das condições do sistema.

## 3. Controle de memória (Memory Management)

C++ oferece controle detalhado sobre a memória utilizada pelos programas.

O programador pode trabalhar com:

- Variáveis locais.
- Ponteiros.
- Referências.
- Alocação dinâmica.
- Gerenciamento automático de recursos.
- Smart pointers.

Esse controle é importante em aplicações que precisam utilizar memória de maneira eficiente.

### Exemplo com ponteiros

```cpp
#include <iostream>

int main() {
    int numero = 100;

    int* ponteiro = &numero;

    std::cout << "Valor: " << numero << '\n';
    std::cout << "Endereço: " << ponteiro << '\n';
    std::cout << "Valor apontado: " << *ponteiro << '\n';

    return 0;
}
```

### Explicação

- `numero` armazena o valor `100`.
- `&numero` obtém o endereço de memória da variável.
- `ponteiro` armazena esse endereço.
- `*ponteiro` acessa o valor armazenado naquele endereço.

C++ também oferece ferramentas modernas para reduzir erros de gerenciamento de memória.

### Exemplo com smart pointer

```cpp
#include <iostream>
#include <memory>

int main() {
    std::unique_ptr<int> numero = std::make_unique<int>(100);

    std::cout << *numero << '\n';

    return 0;
}
```

Nesse exemplo, `std::unique_ptr` gerencia automaticamente o tempo de vida do objeto apontado.

## 4. Desenvolvimento de jogos (Game Development)

C++ é muito utilizada no desenvolvimento de jogos eletrônicos.

Isso acontece porque jogos podem exigir:

- Processamento de gráficos 3D.
- Física e colisões.
- Inteligência artificial.
- Animações.
- Processamento de áudio.
- Comunicação em rede.
- Atualização de milhares de elementos durante a execução.

### Exemplos de tecnologias

- Unreal Engine.
- Godot (partes de sua implementação).
- SFML.
- SDL.
- OpenGL.

### Exemplo simples de lógica de jogo

```cpp
#include <iostream>

int main() {
    int vida = 100;
    int dano = 25;

    vida -= dano;

    std::cout << "Vida do personagem: " << vida << '\n';

    if (vida > 0) {
        std::cout << "Personagem continua vivo!\n";
    } else {
        std::cout << "Personagem derrotado!\n";
    }

    return 0;
}
```

Esse exemplo demonstra uma operação simples de gerenciamento de vida de um personagem.

## 5. Portabilidade (Portability)

C++ pode ser utilizada em diferentes sistemas operacionais e arquiteturas de hardware.

Entre os sistemas compatíveis estão:

- Windows.
- Linux.
- macOS.
- Android.
- Sistemas embarcados.

Um mesmo código pode ser compilado em diferentes plataformas, desde que as dependências e os recursos utilizados sejam compatíveis.

### Exemplo

```cpp
#include <iostream>

int main() {
    std::cout << "Programa multiplataforma!\n";

    return 0;
}
```

Esse programa utiliza recursos da biblioteca padrão do C++ e pode ser compilado em diferentes sistemas.

## 6. Programação multiparadigma (Multi-Paradigm Programming)

C++ permite utilizar diferentes estilos de programação.

### 6.1. Programação procedural

Organiza o código por meio de funções e procedimentos.

```cpp
#include <iostream>

int somar(int a, int b) {
    return a + b;
}

int main() {
    std::cout << somar(10, 20) << '\n';

    return 0;
}
```

### 6.2. Programação orientada a objetos

Organiza o código utilizando classes e objetos.

```cpp
#include <iostream>

class Animal {
public:
    void emitirSom() {
        std::cout << "Som de animal\n";
    }
};

int main() {
    Animal cachorro;

    cachorro.emitirSom();

    return 0;
}
```

### 6.3. Programação genérica

Utiliza templates para criar funções e classes reutilizáveis.

```cpp
#include <iostream>

template <typename T>
T multiplicar(T a, T b) {
    return a * b;
}

int main() {
    std::cout << multiplicar(5, 4) << '\n';
    std::cout << multiplicar(2.5, 2.0) << '\n';

    return 0;
}
```

## 7. Biblioteca padrão (STL)

C++ possui uma biblioteca padrão que disponibiliza estruturas de dados e algoritmos prontos para utilização.

A Standard Template Library (STL) é uma parte importante desse ecossistema.

Entre seus principais recursos estão:

- `std::vector`: vetor dinâmico.
- `std::array`: array de tamanho fixo.
- `std::string`: manipulação de textos.
- `std::map`: estrutura de chave e valor ordenada.
- `std::set`: coleção de elementos únicos.
- `std::queue`: fila.
- `std::stack`: pilha.
- `std::sort`: ordenação.
- `std::find`: busca de elementos.

### Exemplo com std::vector

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numeros = {10, 20, 30, 40, 50};

    for (int numero : numeros) {
        std::cout << numero << '\n';
    }

    return 0;
}
```

### Explicação

- `std::vector<int>` cria um vetor dinâmico de números inteiros.
- Os elementos são inicializados com valores.
- O `for` baseado em intervalo percorre todos os elementos.
- `numero` recebe cada elemento durante a iteração.

## 8. Aplicações científicas e engenharia

C++ é utilizada em aplicações que precisam executar cálculos complexos e processar grandes quantidades de dados.

Exemplos de áreas:

- Simulações físicas.
- Engenharia mecânica.
- Engenharia aeroespacial.
- Modelagem matemática.
- Processamento de imagens.
- Computação de alto desempenho.

### Exemplo de cálculo matemático

```cpp
#include <iostream>
#include <cmath>

int main() {
    double raio = 5.0;

    double area = M_PI * std::pow(raio, 2);

    std::cout << "Área do círculo: " << area << '\n';

    return 0;
}
```

**Observação:** `M_PI` não faz parte do padrão C++ em todas as implementações. Em projetos portáveis, pode-se definir uma constante própria para PI ou utilizar `std::numbers::pi` a partir do C++20.

## 9. Ecossistema e bibliotecas

C++ possui um grande ecossistema de bibliotecas e ferramentas.

Alguns exemplos:

| Biblioteca ou tecnologia | Utilização |
|---|---|
| Boost | Recursos e bibliotecas adicionais |
| Qt | Aplicações com interfaces gráficas |
| OpenCV | Processamento de imagens e visão computacional |
| SFML | Desenvolvimento de jogos e multimídia |
| SDL | Áudio, vídeo e entrada de dispositivos |
| Eigen | Álgebra linear |
| fmt | Formatação de textos |
| GoogleTest | Testes automatizados |

Essas bibliotecas permitem desenvolver aplicações complexas sem precisar implementar todos os recursos do zero.

## 10. Quando escolher C++?

C++ é uma boa escolha quando o projeto exige:

- Alto desempenho.
- Controle de memória.
- Baixa latência.
- Processamento intensivo.
- Desenvolvimento de motores gráficos.
- Aplicações que precisam interagir diretamente com hardware.
- Sistemas com requisitos rigorosos de eficiência.

Entretanto, nem todo projeto precisa utilizar C++.

Para aplicações web convencionais, por exemplo, linguagens como JavaScript, TypeScript, Python e Java podem oferecer desenvolvimento mais simples e produtivo.

## 11. C++ comparado a outras linguagens

| Característica | C++ | Python | Java | JavaScript |
|---|---|---|---|---|
| Compilação | Tradicionalmente compilada | Interpretada/bytecode | Bytecode/JIT | JIT em engines modernas |
| Tipagem | Estática | Dinâmica | Estática | Dinâmica |
| Desempenho | Alto potencial | Geralmente menor | Alto potencial | Alto potencial |
| Controle de memória | Detalhado | Gerenciado | Gerenciado | Gerenciado |
| Orientação a objetos | Sim | Sim | Sim | Sim |
| Templates/generics | Templates | Não possui templates equivalentes | Generics | Generics via TypeScript |

**Observação:** as diferenças de desempenho dependem da implementação, do programa e das condições de execução.

## 12. Exercício prático

Crie um programa que simule o consumo de memória de um pequeno sistema de armazenamento.

O programa deverá:

1. Criar um vetor de números inteiros.
2. Inserir cinco valores.
3. Percorrer o vetor.
4. Calcular a soma dos valores.
5. Exibir o resultado.

### Exemplo de solução

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> valores = {10, 20, 30, 40, 50};

    int soma = 0;

    for (int valor : valores) {
        soma += valor;
    }

    std::cout << "Soma dos valores: " << soma << '\n';

    return 0;
}
```

### Saída esperada

```text
Soma dos valores: 150
```

## 13. Resumo

C++ é uma linguagem muito utilizada porque oferece uma combinação de desempenho, controle, flexibilidade e recursos avançados.

Suas principais vantagens são:

- Alto desempenho.
- Controle de memória.
- Desenvolvimento de jogos.
- Programação multiparadigma.
- Portabilidade.
- Biblioteca padrão abrangente.
- Grande ecossistema de bibliotecas.

C++ é especialmente relevante para quem deseja trabalhar com desenvolvimento de jogos, sistemas, engenharia, computação gráfica e aplicações de alto desempenho.

## 14. Referências

- [ISO C++](https://isocpp.org/)
- [cppreference — C++](https://en.cppreference.com/w/)
- [LearnCpp](https://www.learncpp.com/)
- [Roadmap.sh — C++](https://roadmap.sh/cpp)
