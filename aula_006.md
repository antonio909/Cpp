# Instalando C++

Instalar C++ significa preparar o computador para escrever, compilar, executar e depurar programas desenvolvidos nessa linguagem.

Diferentemente de algumas linguagens que possuem um interpretador próprio, C++ normalmente utiliza um **compilador**, responsável por transformar o código-fonte em um programa executável.

Neste guia, vamos aprender a instalar e configurar o ambiente C++ no Windows, utilizando ferramentas gratuitas.

## 1. O que precisamos instalar?

Para começar a programar em C++, precisamos de três ferramentas principais:

| Ferramenta | Função |
|---|---|
| Editor de código | Permite escrever e organizar o código-fonte. |
| Compilador C++ | Transforma o código C++ em um programa executável. |
| Depurador (Debugger) | Ajuda a encontrar e corrigir erros no programa. |

Uma combinação bastante utilizada é:

- **Visual Studio Code (VS Code):** editor de código.
- **GCC/G++:** compilador C e C++.
- **GDB:** depurador.
- **MSYS2:** ambiente que facilita a instalação do GCC, GDB e outras ferramentas no Windows.

> **Observação:** o VS Code sozinho não compila programas C++. É necessário instalar um compilador separadamente.

## 2. Instalando o Visual Studio Code

O Visual Studio Code é um editor gratuito que oferece recursos para desenvolvimento em diversas linguagens, incluindo C++.

### Passo 1 — Baixar o VS Code

Acesse o site oficial:

https://code.visualstudio.com/

1. Clique em **Download for Windows**.
2. Aguarde o download.
3. Execute o instalador.
4. Aceite os termos de licença.
5. Siga as etapas da instalação.

### Passo 2 — Instalar a extensão C/C++

Depois de instalar e abrir o VS Code:

1. Abra a seção Extensions.
2. Pesquise por `C/C++`.
3. Selecione a extensão publicada pela Microsoft.
4. Clique em Install.

A extensão oferece recursos como:

- Autocompletar código.
- Identificação de erros.
- Navegação entre arquivos.
- Integração com depuradores.
- Recursos de IntelliSense.

## 3. Instalando o compilador C++ com MSYS2

No Windows, uma maneira prática de instalar o GCC e o GDB é utilizar o MSYS2.

O MSYS2 fornece um ambiente de ferramentas de desenvolvimento e um gerenciador de pacotes chamado `pacman`.

### Passo 1 — Baixar o MSYS2

Acesse:

https://www.msys2.org/

1. Baixe o instalador.
2. Execute o arquivo.
3. Siga as instruções.
4. Ao terminar, abra o terminal **MSYS2 UCRT64**.

### Passo 2 — Atualizar os pacotes

No terminal UCRT64, execute:

```bash
pacman -Syu
```

Esse comando atualiza os pacotes do ambiente.

Se o terminal solicitar que seja fechado, feche-o, abra novamente o MSYS2 UCRT64 e execute:

```bash
pacman -Su
```

### Passo 3 — Instalar o GCC, G++ e GDB

Execute:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-gdb
```

Esse comando instala:

| Pacote | Descrição |
|---|---|
| GCC | Coleção de compiladores GNU. |
| G++ | Compilador utilizado para programas C++. |
| GDB | Ferramenta de depuração. |
| Base-devel | Ferramentas básicas para desenvolvimento. |

## 4. Configurando o PATH do Windows

Depois da instalação, precisamos permitir que o Windows encontre o compilador a partir do PowerShell ou do terminal do VS Code.

O diretório padrão do compilador UCRT64 é:

```text
C:\msys64\ucrt64\bin
```

### Passo 1 — Abrir as variáveis de ambiente

1. Abra o menu Iniciar.
2. Pesquise por `Editar as variáveis de ambiente do sistema`.
3. Abra a opção correspondente.
4. Clique em **Variáveis de Ambiente**.
5. Na seção de variáveis do usuário, selecione `Path`.
6. Clique em Editar.
7. Clique em Novo.
8. Adicione:

```text
C:\msys64\ucrt64\bin
```

9. Confirme as alterações.

### Passo 2 — Verificar a instalação

Feche e abra novamente o PowerShell.

Execute:

```powershell
g++ --version
```

Se o compilador estiver instalado corretamente, será exibida a versão do G++.

Também podemos verificar o GDB:

```powershell
gdb --version
```

E o GCC:

```powershell
gcc --version
```

Se os comandos forem reconhecidos, o ambiente está preparado.

## 5. Criando seu primeiro projeto C++

Agora que temos o compilador instalado, podemos criar nosso primeiro programa.

### Passo 1 — Criar uma pasta

Crie uma pasta chamada:

```text
cpp-projects
```

Dentro dela, crie outra pasta chamada:

```text
hello-world
```

A estrutura ficará assim:

```text
cpp-projects/
└── hello-world/
```

### Passo 2 — Abrir a pasta no VS Code

1. Abra o Visual Studio Code.
2. Clique em **File → Open Folder**.
3. Selecione a pasta `hello-world`.
4. Crie um arquivo chamado `main.cpp`.

A extensão `.cpp` identifica um arquivo de código-fonte C++.

### Passo 3 — Escrever o código

Dentro de `main.cpp`, escreva:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;

    return 0;
}
```

Esse programa imprime a mensagem `Hello, World!` no terminal.

## 6. Compilando um programa C++

Agora precisamos transformar o código-fonte em um executável.

Abra o terminal integrado do VS Code:

- Atalho: `Ctrl + Shift + '` (dependendo do teclado, pode ser necessário ajustar).
- Ou acesse **Terminal → New Terminal**.

Execute:

```powershell
g++ main.cpp -o programa.exe
```

Entendendo o comando:

| Parte | Significado |
|---|---|
| `g++` | Executa o compilador C++. |
| `main.cpp` | Arquivo que contém o código-fonte. |
| `-o` | Define o nome do arquivo de saída. |
| `programa.exe` | Nome do executável gerado. |

Se não houver erros, será criado o arquivo:

```text
programa.exe
```

## 7. Executando o programa

No PowerShell, execute:

```powershell
.\programa.exe
```

Resultado esperado:

```text
Hello, World!
```

Você acabou de compilar e executar seu primeiro programa C++.

## 8. Utilizando diferentes padrões do C++

C++ possui diferentes versões, que introduzem novos recursos à linguagem.

Algumas versões importantes:

| Versão | Ano | Características |
|---|---:|---|
| C++98 | 1998 | Primeira padronização internacional. |
| C++03 | 2003 | Correções e melhorias do padrão anterior. |
| C++11 | 2011 | `auto`, lambdas, smart pointers e outras novidades. |
| C++14 | 2014 | Melhorias introduzidas no C++11. |
| C++17 | 2017 | `std::optional`, `std::filesystem` e outros recursos. |
| C++20 | 2020 | Concepts, ranges e coroutines. |
| C++23 | 2023 | Novas funcionalidades e melhorias da linguagem. |

Para escolher um padrão, podemos utilizar a opção `-std` do compilador.

Exemplo utilizando C++20:

```powershell
g++ -std=c++20 main.cpp -o programa.exe
```

Exemplo utilizando C++23:

```powershell
g++ -std=c++23 main.cpp -o programa.exe
```

O suporte a cada recurso depende da versão do compilador instalada.

## 9. Problemas comuns durante a instalação

### Problema 1 — `g++` não é reconhecido

Mensagem:

```text
g++ : O termo 'g++' não é reconhecido
```

Possíveis causas:

- O GCC não foi instalado.
- O diretório do compilador não foi adicionado ao PATH.
- O terminal foi aberto antes da alteração do PATH.

**Solução:**

Verifique se o diretório abaixo existe:

```text
C:\msys64\ucrt64\bin
```

Confirme também se ele está cadastrado nas variáveis de ambiente do Windows.

Feche e abra novamente o terminal.

### Problema 2 — Arquivo não encontrado

Mensagem:

```text
g++: error: main.cpp: No such file or directory
```

Isso significa que o compilador não encontrou o arquivo indicado.

**Solução:**

Verifique se o terminal está aberto na pasta correta e se o arquivo realmente se chama `main.cpp`.

Para verificar os arquivos da pasta no PowerShell:

```powershell
dir
```

### Problema 3 — Erros de sintaxe

Exemplo:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!"

    return 0;
}
```

O código apresenta um erro porque falta o ponto e vírgula (`;`) depois da instrução `std::cout`.

Forma correta:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!";

    return 0;
}
```

O compilador identifica muitos erros de sintaxe e informa onde eles ocorreram.

## 10. Outras ferramentas úteis para desenvolvimento C++

Além das ferramentas principais, existem outras que podem facilitar o desenvolvimento.

| Ferramenta | Utilização |
|---|---|
| CMake | Gerenciamento e configuração de projetos. |
| Make | Automação da compilação. |
| Ninja | Sistema de construção rápido. |
| Git | Controle de versões. |
| Clang | Compilador alternativo para C e C++. |
| GDB | Depuração de programas. |

Não é necessário instalar todas essas ferramentas imediatamente. Para começar, VS Code, GCC e GDB são suficientes.

## 11. Exercício prático

Depois de configurar o ambiente, tente desenvolver uma pequena calculadora.

O programa deve:

1. Solicitar dois números ao usuário.
2. Calcular a soma.
3. Calcular a subtração.
4. Calcular a multiplicação.
5. Calcular a divisão, verificando se o divisor é diferente de zero.

Exemplo inicial:

```cpp
#include <iostream>

int main() {
    double numero1;
    double numero2;

    std::cout << "Digite o primeiro numero: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo numero: ";
    std::cin >> numero2;

    std::cout << "Soma: "
              << numero1 + numero2 << std::endl;

    std::cout << "Subtracao: "
              << numero1 - numero2 << std::endl;

    std::cout << "Multiplicacao: "
              << numero1 * numero2 << std::endl;

    if (numero2 != 0) {
        std::cout << "Divisao: "
                  << numero1 / numero2 << std::endl;
    } else {
        std::cout << "Nao e possivel dividir por zero."
                  << std::endl;
    }

    return 0;
}
```

Compile:

```powershell
g++ -std=c++20 main.cpp -o calculadora.exe
```

Execute:

```powershell
.\calculadora.exe
```

## 12. Checklist de instalação

Antes de começar a estudar os próximos tópicos, confira se tudo está funcionando:

- [ ] Visual Studio Code instalado.
- [ ] Extensão C/C++ instalada.
- [ ] MSYS2 instalado.
- [ ] GCC/G++ instalado.
- [ ] GDB instalado.
- [ ] Diretório do compilador adicionado ao PATH.
- [ ] Comando `g++ --version` funcionando.
- [ ] Primeiro programa compilado.
- [ ] Primeiro programa executado.

## 13. Resumo

Instalar C++ envolve preparar um ambiente de desenvolvimento com editor, compilador e ferramentas de depuração.

Neste guia, utilizamos:

- **Visual Studio Code:** para escrever código.
- **MSYS2:** para instalar ferramentas de desenvolvimento.
- **GCC/G++:** para compilar programas C++.
- **GDB:** para depurar programas.

Depois da instalação, aprendemos a criar um arquivo `.cpp`, compilar o código com `g++` e executar o programa pelo PowerShell.

Com o ambiente configurado, já podemos começar a estudar os fundamentos da linguagem C++ e desenvolver projetos próprios.

## 14. Referências

- [MSYS2 — Site oficial](https://www.msys2.org/)
- [GCC — Documentação oficial](https://gcc.gnu.org/onlinedocs/)
- [Visual Studio Code — C++](https://code.visualstudio.com/docs/languages/cpp)
- [Microsoft C++ — Documentação](https://learn.microsoft.com/en-us/cpp/)
- [LearnCpp — Tutorial de C++](https://www.learncpp.com/)
- [cppreference — C++](https://en.cppreference.com/w/)
