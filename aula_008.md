# Executando seu Primeiro Programa em C++

## 1. Introdução

Depois de instalar o compilador C++ e configurar um editor de código ou IDE, chegou o momento de executar nosso primeiro programa.

Executar um programa C++ envolve algumas etapas importantes:

1. Escrever o código-fonte.
2. Salvar o arquivo com a extensão `.cpp`.
3. Compilar o código utilizando um compilador.
4. Gerar um arquivo executável.
5. Executar o programa.
6. Visualizar os resultados no terminal.

Neste capítulo, vamos entender cada etapa e aprender como compilar e executar programas C++ utilizando o GCC (G++), o Visual Studio Code e o PowerShell.

## 2. Criando o primeiro programa C++

Vamos começar criando um programa simples que exibe uma mensagem na tela.

Crie um arquivo chamado:

```text
main.cpp
```

Dentro dele, escreva o seguinte código:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;

    return 0;
}
```

Esse é um dos programas mais conhecidos entre pessoas que estão aprendendo uma nova linguagem de programação.

O programa simplesmente exibe a mensagem:

```text
Hello, World!
```

## 3. Entendendo o código

Vamos analisar cada parte do programa.

### 3.1 Diretiva `#include`

```cpp
#include <iostream>
```

A diretiva `#include` permite incluir bibliotecas ou arquivos de cabeçalho necessários para utilizar determinadas funcionalidades.

Neste exemplo, estamos incluindo a biblioteca padrão `iostream`.

Ela fornece recursos para operações de entrada e saída de dados.

Entre os recursos disponíveis estão:

- `std::cout`: saída de dados.
- `std::cin`: entrada de dados.
- `std::cerr`: saída de mensagens de erro.
- `std::clog`: saída de mensagens de registro.

### 3.2 Função `main()`

```cpp
int main() {

}
```

A função `main()` é o ponto de entrada de um programa C++ executável.

Isso significa que a execução do programa começa nessa função.

Todo programa C++ executável precisa possuir uma função `main()` definida corretamente.

### 3.3 Instrução `std::cout`

```cpp
std::cout << "Hello, World!";
```

`std::cout` é utilizado para enviar informações para a saída padrão, normalmente o terminal.

O operador `<<` envia o conteúdo para o fluxo de saída.

Podemos imprimir diferentes tipos de informações:

```cpp
#include <iostream>

int main() {
    std::cout << "Aprendendo C++" << std::endl;
    std::cout << 100 << std::endl;
    std::cout << 25.5 << std::endl;

    return 0;
}
```

Resultado:

```text
Aprendendo C++
100
25.5
```

### 3.4 `std::endl`

```cpp
std::cout << "Hello, World!" << std::endl;
```

`std::endl` insere uma quebra de linha e também solicita que o fluxo seja descarregado (flush).

Outra maneira de inserir uma quebra de linha é utilizar `\n`:

```cpp
std::cout << "Hello, World!\n";
```

A diferença é que `\n` apenas insere a quebra de linha, enquanto `std::endl` também realiza o flush do fluxo.

Em muitos casos, utilizar `\n` é suficiente.

### 3.5 `return 0`

```cpp
return 0;
```

O comando `return` encerra a função e devolve um valor.

Na função `main()`, o valor retornado representa o código de saída do programa.

Por convenção:

- `0`: indica que o programa terminou com sucesso.
- Valores diferentes de `0`: normalmente indicam algum tipo de erro.

Exemplo:

```cpp
int main() {
    return 0;
}
```

## 4. O que é um código-fonte?

O código-fonte é o conjunto de instruções escritas pelo programador utilizando uma linguagem de programação.

Em C++, os arquivos de código-fonte geralmente utilizam extensões como:

| Extensão | Descrição |
|---|---|
| `.cpp` | Arquivo de implementação C++. |
| `.cc` | Outra extensão utilizada para código C++. |
| `.cxx` | Outra extensão utilizada para código C++. |
| `.hpp` | Arquivo de cabeçalho C++. |
| `.h` | Arquivo de cabeçalho, também utilizado em projetos C++. |

Exemplo:

```text
projeto/
├── main.cpp
├── calculadora.cpp
├── calculadora.hpp
└── utilitarios.cpp
```

O código-fonte ainda não é o programa executável. Ele precisa passar pelo processo de compilação.

## 5. O que é compilação?

Compilação é o processo de transformar o código-fonte em código executável pela máquina.

Em C++, esse processo normalmente envolve diferentes etapas:

1. Pré-processamento.
2. Compilação.
3. Montagem (Assembly).
4. Ligação (Linking).

Fluxo simplificado:

```text
Código-fonte (.cpp)
        |
        v
Pré-processamento
        |
        v
Compilação
        |
        v
Código Assembly
        |
        v
Montagem
        |
        v
Arquivo objeto (.o ou .obj)
        |
        v
Linking
        |
        v
Programa executável (.exe)
```

Cada etapa possui uma responsabilidade específica.

## 6. Entendendo as etapas da compilação

### 6.1 Pré-processamento

O pré-processador trata diretivas que começam com `#`, como:

```cpp
#include <iostream>
#define PI 3.14159
```

Entre suas responsabilidades estão:

- Incluir arquivos de cabeçalho.
- Expandir macros.
- Processar diretivas condicionais.
- Preparar o código para as próximas etapas.

### 6.2 Compilação

Nessa etapa, o compilador analisa o código C++ e o transforma em uma representação de baixo nível, normalmente código Assembly.

O compilador também verifica diversos aspectos da linguagem, como:

- Sintaxe.
- Tipos de dados.
- Declarações.
- Expressões.
- Regras da linguagem.

Se encontrar erros, poderá interromper o processo e apresentar mensagens indicando os problemas.

### 6.3 Montagem (Assembly)

O montador transforma o código Assembly em código de máquina organizado em um arquivo objeto.

Exemplos de extensões:

- `.o` em muitos ambientes Unix.
- `.obj` no ambiente Microsoft.

### 6.4 Linking

O linker, ou ligador, combina arquivos objeto e bibliotecas necessárias para gerar o programa executável.

Essa etapa resolve referências entre diferentes partes do programa.

Por exemplo, quando uma função é declarada em um arquivo e implementada em outro, o linker ajuda a conectar essas partes.

## 7. Compilando o primeiro programa com G++

Agora vamos compilar nosso programa utilizando o GCC.

Abra o terminal na pasta onde está o arquivo `main.cpp`.

Execute:

```powershell
g++ main.cpp -o programa.exe
```

Vamos entender o comando:

| Elemento | Significado |
|---|---|
| `g++` | Executa o compilador C++. |
| `main.cpp` | Arquivo de código-fonte. |
| `-o` | Define o nome do arquivo de saída. |
| `programa.exe` | Nome do executável gerado. |

Se não houver erros, o compilador criará:

```text
programa.exe
```

Esse arquivo contém o programa compilado e poderá ser executado no Windows.

### 7.1 Utilizando um padrão específico do C++

Podemos escolher a versão do padrão C++ durante a compilação.

Por exemplo, para utilizar C++20:

```powershell
g++ -std=c++20 main.cpp -o programa.exe
```

Para utilizar C++23:

```powershell
g++ -std=c++23 main.cpp -o programa.exe
```

A disponibilidade dos recursos depende da versão do compilador instalado.

## 8. Executando o primeiro programa

Depois de compilar o código, precisamos executar o arquivo gerado.

No PowerShell, utilize:

```powershell
.\programa.exe
```

Resultado:

```text
Hello, World!
```

Parabéns! Você acabou de executar seu primeiro programa C++.

### 8.1 Por que utilizar `.\`?

No PowerShell, o prefixo `.\` indica que queremos executar um arquivo localizado no diretório atual.

Por isso:

```powershell
.\programa.exe
```

significa executar o arquivo `programa.exe` presente na pasta atual.

## 9. Compilando e executando diretamente

Podemos combinar a compilação e a execução em sequência.

Exemplo no PowerShell:

```powershell
g++ main.cpp -o programa.exe

if ($LASTEXITCODE -eq 0) {
    .\programa.exe
}
```

A variável automática `$LASTEXITCODE` contém o código de saída do último programa executado.

Nesse exemplo, o programa somente será executado se a compilação terminar com sucesso.

## 10. Utilizando o Visual Studio Code

Também podemos compilar e executar programas diretamente pelo terminal integrado do VS Code.

### Passo 1 — Abrir o projeto

Abra o VS Code e selecione a pasta que contém o arquivo `main.cpp`.

### Passo 2 — Abrir o terminal

Utilize:

```text
Terminal → New Terminal
```

Ou o atalho:

```text
Ctrl + Shift + `
```

### Passo 3 — Compilar

Execute:

```powershell
g++ -std=c++20 main.cpp -o programa.exe
```

### Passo 4 — Executar

Execute:

```powershell
.\programa.exe
```

O resultado aparecerá no terminal integrado.

## 11. Trabalhando com entrada de dados

Até agora, nossos programas apenas exibiram informações.

Entretanto, podemos criar programas que recebem informações digitadas pelo usuário.

Para isso, utilizamos `std::cin`.

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade;

    std::cout << "Digite sua idade: ";
    std::cin >> idade;

    std::cout << "Sua idade e: " << idade << std::endl;

    return 0;
}
```

Possível execução:

```text
Digite sua idade: 18
Sua idade e: 18
```

### Entendendo `std::cin`

```cpp
std::cin >> idade;
```

`std::cin` recebe informações da entrada padrão, normalmente o teclado.

O operador `>>` extrai o valor digitado e o armazena na variável indicada.

## 12. Criando um programa com operações matemáticas

Agora vamos desenvolver um programa um pouco mais completo.

O objetivo será solicitar dois números e apresentar a soma.

```cpp
#include <iostream>

int main() {
    double numero1;
    double numero2;
    double resultado;

    std::cout << "Digite o primeiro numero: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo numero: ";
    std::cin >> numero2;

    resultado = numero1 + numero2;

    std::cout << "Resultado: " << resultado << std::endl;

    return 0;
}
```

Possível execução:

```text
Digite o primeiro numero: 10
Digite o segundo numero: 20
Resultado: 30
```

Nesse exemplo, utilizamos:

- `double`: tipo de dado para números com casas decimais.
- `std::cin`: entrada de dados.
- `std::cout`: saída de dados.
- `+`: operador de adição.
- `return 0`: finalização bem-sucedida do programa.

## 13. O que são erros de compilação?

Erros de compilação acontecem quando o compilador encontra algum problema que impede a geração do programa executável.

Exemplo:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!"

    return 0;
}
```

Nesse exemplo, esquecemos o ponto e vírgula (`;`) depois da instrução `std::cout`.

Ao compilar, o compilador apresentará uma mensagem de erro.

### Forma correta

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!";

    return 0;
}
```

O ponto e vírgula é utilizado para encerrar diversas instruções em C++.

## 14. O que são erros de execução?

Erros de execução acontecem enquanto o programa está sendo executado.

Um programa pode compilar corretamente e ainda apresentar problemas durante sua execução.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;
    int divisor = 0;

    std::cout << numero / divisor << std::endl;

    return 0;
}
```

Esse exemplo tenta realizar uma divisão inteira por zero, o que causa comportamento indefinido em C++.

Uma maneira de evitar esse problema é verificar o divisor:

```cpp
#include <iostream>

int main() {
    int numero = 10;
    int divisor = 0;

    if (divisor != 0) {
        std::cout << numero / divisor << std::endl;
    } else {
        std::cout << "Nao e possivel dividir por zero." << std::endl;
    }

    return 0;
}
```

## 15. Diferença entre Compilar, Executar e Depurar

Esses três conceitos são fundamentais no desenvolvimento C++.

| Conceito | Descrição |
|---|---|
| Compilar | Transformar o código-fonte em um programa executável. |
| Executar | Iniciar o programa para que suas instruções sejam realizadas. |
| Depurar | Analisar a execução do programa para identificar problemas. |

### Exemplo de fluxo de desenvolvimento

```text
Escrever código
      |
      v
Salvar arquivo
      |
      v
Compilar
      |
      v
Existem erros?
   /       \
 Sim       Não
  |         |
  v         v
Corrigir   Executar
  |         |
  |         v
  |      Resultado
  |         |
  +---------+
```

## 16. Exercícios práticos

### Exercício 1 — Hello World

Crie um programa que exiba:

```text
Estou aprendendo C++!
```

### Exercício 2 — Informações pessoais fictícias

Crie um programa que solicite um nome e uma idade e apresente as informações digitadas.

Utilize:

- `std::string`.
- `std::cin` ou `std::getline`.
- `std::cout`.

### Exercício 3 — Calculadora de soma

Crie um programa que receba dois números e apresente o resultado da soma.

### Exercício 4 — Operações matemáticas

Crie um programa que receba dois números e apresente:

- Soma.
- Subtração.
- Multiplicação.
- Divisão, verificando se o divisor é diferente de zero.

### Exercício 5 — Compilação

Compile um programa utilizando C++20.

Utilize:

```powershell
g++ -std=c++20 main.cpp -o exercicio.exe
```

Depois execute:

```powershell
.\exercicio.exe
```

## 17. Problemas comuns

### Problema 1 — G++ não reconhecido

Mensagem:

```text
g++ não é reconhecido como um comando
```

Possíveis causas:

- GCC não instalado.
- Diretório do compilador ausente no PATH.
- Terminal aberto antes da configuração do PATH.

Solução:

Verifique a instalação do GCC e configure corretamente o PATH do Windows.

### Problema 2 — Arquivo não encontrado

Mensagem:

```text
g++: error: main.cpp: No such file or directory
```

Possível causa:

O terminal está aberto em uma pasta diferente daquela onde está o arquivo.

Solução:

Utilize:

```powershell
dir
```

para verificar os arquivos presentes no diretório atual.

### Problema 3 — Erro durante a compilação

Possíveis causas:

- Falta de ponto e vírgula.
- Chaves abertas ou fechadas incorretamente.
- Variáveis não declaradas.
- Tipos incompatíveis.
- Funções utilizadas incorretamente.

Solução:

Leia a mensagem do compilador, localize a linha indicada e revise o código.

### Problema 4 — Executável não encontrado

Mensagem:

```text
.\programa.exe : O termo não é reconhecido
```

Possíveis causas:

- A compilação não foi concluída.
- O executável possui outro nome.
- O terminal está em outra pasta.

Solução:

Verifique se o arquivo executável foi criado utilizando:

```powershell
dir
```

## 18. Resumo

Neste capítulo, aprendemos como executar nosso primeiro programa C++.

Os principais conceitos estudados foram:

- Código-fonte: arquivo que contém as instruções do programa.
- Compilação: processo de transformação do código-fonte.
- Pré-processamento: tratamento das diretivas do pré-processador.
- Assembly: representação de baixo nível utilizada na geração de código de máquina.
- Linking: ligação dos arquivos objeto e bibliotecas.
- Executável: arquivo que pode ser iniciado pelo sistema operacional.
- `std::cout`: saída de informações.
- `std::cin`: entrada de informações.
- `main()`: ponto de entrada do programa.
- `return 0`: indica finalização bem-sucedida.

Também aprendemos a compilar programas utilizando G++ e executá-los pelo PowerShell e pelo terminal integrado do Visual Studio Code.

## 19. Referências

- [LearnCpp — Introduction to C++](https://www.learncpp.com/)
- [GCC — Compiling C++ Programs](https://gcc.gnu.org/onlinedocs/gcc/Invoking-G_002b_002b.html)
- [Microsoft — C++ Documentation](https://learn.microsoft.com/en-us/cpp/)
- [cppreference — Main Function](https://en.cppreference.com/w/cpp/language/main_function)
- [cppreference — Basic I/O](https://en.cppreference.com/w/cpp/io)
- [C++ Reference](https://en.cppreference.com/w/)
