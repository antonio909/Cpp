# Por que usar C++?

## 1. Por que utilizar C++?

C++ é uma das linguagens de programação mais utilizadas em projetos que exigem alto desempenho, eficiência e controle sobre os recursos do computador.

Ela oferece ferramentas para desenvolver desde pequenos programas até sistemas complexos, como motores de jogos, sistemas operacionais, aplicações científicas e softwares de engenharia.

Uma das principais razões para utilizar C++ é a possibilidade de combinar desempenho, flexibilidade e diferentes paradigmas da programação.

## 2. Alto desempenho (High Performance)

Uma das maiores vantagens do C++ é seu alto desempenho.

Como o C++ é uma linguagem compilada, seu código pode ser transformado em instruções executadas diretamente pelo processador, sem depender necessariamente de uma máquina virtual ou interpretador em tempo de execução.

Isso permite criar aplicações que utilizam os recursos do computador de maneira eficiente.

### Exemplo

```cpp
#include <iostream>
#include <chrono>

int main() {
  auto inicio = std::chrono::high_resolution_clock::now();

  long long soma = 0;

  for (int i = 0; i < 100000; i++) {}
}
```
