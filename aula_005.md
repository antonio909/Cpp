
# Setting Up Your Environment — Configurando o Ambiente C++

## 1. Introdução

Antes de começar a programar em C++, precisamos preparar um ambiente de desenvolvimento.

Um ambiente de desenvolvimento é o conjunto de ferramentas utilizadas para escrever, compilar, executar, testar e depurar programas.

Para desenvolver aplicações em C++, normalmente precisamos de:

- Editor de código ou IDE.
- Compilador C++.
- Depurador (Debugger).
- Terminal.
- Ferramentas de construção (Build Tools).

Neste material, utilizaremos o Windows como sistema operacional e o Visual Studio Code como editor.

## 2. Ferramentas necessárias

### 2.1. Editor de código

Um editor de código é um programa utilizado para escrever e organizar arquivos contendo código-fonte.

Alguns exemplos:

| Editor | Descrição |
|---|---|
| Visual Studio Code | Editor leve e extensível |
| Visual Studio | IDE completa para desenvolvimento |
| CLion | IDE especializada em C e C++ |
| Code::Blocks | IDE gratuita para C e C++ |

Neste material, utilizaremos o Visual Studio Code.

### 2.2. Compilador C++

O compilador transforma o código-fonte C++ em código executável.

Alguns compiladores conhecidos:

- GCC (GNU Compiler Collection).
- Clang.
- MSVC (Microsoft Visual C++).

Para este ambiente, utilizaremos o GCC através do MSYS2.

### 2.3. Depurador (Debugger)

Um depurador permite executar um programa passo a passo, observar variáveis e investigar erros.

Uma ferramenta comum para desenvolvimento C++ com GCC é o GDB.

Principais funcionalidades:

- Executar o programa passo a passo.
- Criar breakpoints.
- Inspecionar variáveis.
- Observar a execução das funções.
- Investigar erros.

## 3. Instalando o Visual Studio Code

O Visual Studio Code é um editor de código desenvolvido pela Microsoft.

### Etapa 1 — Download

Acesse:

https://code.visualstudio.com/

Baixe a versão para Windows.

### Etapa 2 — Instalação

1. Execute o instalador.
2. Aceite os termos de licença.
3. Escolha o diretório de instalação.
4. Mantenha as opções recomendadas.
5. Finalize a instalação.

A instalação por usuário é uma opção recomendada para a maioria dos casos no Windows.

### Etapa 3 — Verificar instalação

Abra o PowerShell e execute:

```powershell
code --version
```

Se a instalação estiver correta, será exibida a versão do Visual Studio Code.

## 4. Instalando a extensão C/C++

O Visual Studio Code não possui um compilador C++ integrado.

A extensão C/C++ adiciona recursos de desenvolvimento, como:

- Realce de sintaxe.
- IntelliSense.
- Autocompletar código.
- Navegação entre definições.
- Identificação de problemas.
- Integração com depuradores.

### Etapa 1 — Abrir extensões

No Visual Studio Code:

1. Abra a seção Extensions.
2. Pesquise por `C/C++`.
3. Selecione a extensão publicada pela Microsoft.
4. Clique em Install.

Atalho:

```text
Ctrl + Shift + X
```

**Importante:** a extensão oferece recursos de edição e integração, mas não instala automaticamente um compilador.

## 5. Instalando o compilador GCC através do MSYS2

MSYS2 é um ambiente para Windows que disponibiliza ferramentas de desenvolvimento e um gerenciador de pacotes.

Ele permite instalar o GCC, o GDB e outras ferramentas.

### Etapa 1 — Download do MSYS2

Acesse o site oficial:

https://www.msys2.org/

Baixe o instalador e execute-o.

Recomenda-se utilizar o diretório padrão:

```text
C:\msys64
```

### Etapa 2 — Abrir o terminal UCRT64

Depois da instalação:

1. Abra o menu Iniciar do Windows.
2. Pesquise por `MSYS2 UCRT64`.
3. Execute o terminal correspondente.

O ambiente UCRT64 é uma opção recomendada pelo projeto MSYS2 para quem não sabe qual ambiente escolher.

### Etapa 3 — Atualizar os pacotes

No terminal MSYS2 UCRT64, execute:

```bash
pacman -Syu
```

Se o terminal solicitar que seja fechado para concluir a atualização, feche-o, abra novamente o MSYS2 UCRT64 e execute a atualização caso seja solicitado.

### Etapa 4 — Instalar o compilador

Execute:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

Esse comando instala as ferramentas de desenvolvimento necessárias, incluindo:

- GCC.
- G++.
- GDB.
- Binutils.
- Ferramentas de compilação.

Quando aparecer a confirmação da instalação, pressione `Enter` para aceitar os pacotes padrão e depois `Y` para confirmar.

## 6. Configurando a variável PATH

A variável de ambiente `PATH` informa ao Windows quais diretórios devem ser pesquisados quando executamos comandos no terminal.

Precisamos adicionar o diretório do compilador para poder utilizar `g++` diretamente no PowerShell.

### Diretório do GCC

Considerando a instalação padrão do MSYS2:

```text
C:\msys64\ucrt64\bin
```

### Etapa 1 — Abrir as variáveis de ambiente

1. Abra a pesquisa do Windows.
2. Digite `Variáveis de ambiente`.
3. Selecione `Editar as variáveis de ambiente do sistema`.
4. Clique em `Variáveis de Ambiente`.

### Etapa 2 — Editar PATH

Na seção de variáveis do usuário:

1. Selecione `Path`.
2. Clique em `Editar`.
3. Clique em `Novo`.
4. Adicione:

```text
C:\msys64\ucrt64\bin
```

5. Confirme as alterações.

### Etapa 3 — Reiniciar o terminal

Feche o PowerShell e abra uma nova janela.

Isso é necessário para que o terminal reconheça a alteração da variável `PATH`.

## 7. Verificando a instalação

Abra o PowerShell e execute os seguintes comandos:

### Verificar GCC

```powershell
gcc --version
```

### Verificar G++

```powershell
g++ --version
```

### Verificar GDB

```powershell
gdb --version
```

Se os comandos exibirem informações de versão, as ferramentas estão disponíveis no terminal.

O compilador utilizado para os programas C++ será o `g++`.

## 8. Criando o primeiro projeto C++

Agora que temos o ambiente configurado, vamos criar nosso primeiro programa.

### Etapa 1 — Criar uma pasta

Crie uma pasta chamada:

```text
cpp-projects
```

### Etapa 2 — Abrir a pasta no VS Code

Abra o PowerShell e execute:

```powershell
cd $HOME\Documents\cpp-projects
code .
```

O comando `code .` abre a pasta atual no Visual Studio Code.

### Etapa 3 — Criar um arquivo

Dentro do Visual Studio Code:

1. Clique em New File.
2. Crie um arquivo chamado:

```text
main.cpp
```

A extensão `.cpp` identifica um arquivo de código-fonte C++.

## 9. Escrevendo o primeiro programa

Adicione o seguinte código ao arquivo `main.cpp`:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!\n";

    return 0;
}
```

### Explicação

**`#include <iostream>`**

Inclui a biblioteca responsável pelas operações básicas de entrada e saída.

**`int main()`**

Define a função principal do programa.

**`std::cout`**

Exibe informações no terminal.

**`return 0`**

Indica que o programa terminou com sucesso.

## 10. Compilando o programa

Abra o terminal integrado do Visual Studio Code:

```text
Ctrl + `
```

Execute o comando:

```powershell
g++ main.cpp -o programa.exe
```

### Explicação do comando

| Elemento | Significado |
|---|---|
| `g++` | Compilador C++ |
| `main.cpp` | Arquivo de código-fonte |
| `-o` | Define o nome do arquivo de saída |
| `programa.exe` | Executável gerado |

Se não houver erros, o compilador criará o arquivo `programa.exe`.

## 11. Executando o programa

No terminal do Visual Studio Code, execute:

```powershell
.\programa.exe
```

### Saída esperada

```text
Hello, World!
```

Parabéns! Seu primeiro programa C++ foi compilado e executado.

## 12. Entendendo a estrutura do ambiente

Um projeto simples pode apresentar a seguinte estrutura:

```text
cpp-projects/
│
├── main.cpp
│
└── programa.exe
```

Descrição:

| Arquivo | Função |
|---|---|
| `main.cpp` | Código-fonte C++ |
| `programa.exe` | Programa executável |

Em projetos maiores, podemos utilizar pastas adicionais:

```text
meu-projeto/
│
├── src/
│   └── main.cpp
│
├── include/
│
├── build/
│
└── README.md
```

- `src/`: contém os arquivos de implementação.
- `include/`: contém arquivos de cabeçalho.
- `build/`: contém arquivos gerados durante a compilação.
- `README.md`: documentação do projeto.

## 13. Configurando o padrão C++

Podemos informar ao compilador qual versão do padrão C++ queremos utilizar.

Por exemplo, para utilizar C++20:

```powershell
g++ -std=c++20 main.cpp -o programa.exe
```

Para utilizar C++23:

```powershell
g++ -std=c++23 main.cpp -o programa.exe
```

A opção `-std` define o padrão da linguagem utilizado na compilação.

É importante verificar se a versão instalada do compilador oferece suporte aos recursos do padrão escolhido.

## 14. Problemas comuns durante a configuração

### 14.1. Erro: g++ não é reconhecido

Mensagem:

```text
'g++' não é reconhecido como um comando interno
```

Possíveis causas:

- GCC não instalado.
- Diretório incorreto no PATH.
- Terminal aberto antes da alteração do PATH.

Soluções:

1. Verifique se o GCC está instalado.
2. Confira se o diretório `C:\msys64\ucrt64\bin` está no PATH.
3. Feche e abra novamente o terminal.
4. Execute `g++ --version`.

### 14.2. Erro: arquivo não encontrado

Mensagem:

```text
fatal error: main.cpp: No such file or directory
```

Possíveis causas:

- O terminal está em outra pasta.
- O nome do arquivo está incorreto.
- O arquivo ainda não foi salvo.

Solução:

Verifique a pasta atual:

```powershell
Get-Location
```

Liste os arquivos:

```powershell
Get-ChildItem
```

### 14.3. Erro de sintaxe

Exemplo:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!"

    return 0;
}
```

Nesse exemplo, falta o ponto e vírgula depois da instrução `std::cout`.

Código corrigido:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!";

    return 0;
}
```

## 15. Ferramentas adicionais

Depois de configurar o ambiente básico, podemos conhecer outras ferramentas utilizadas no desenvolvimento C++.

| Ferramenta | Finalidade |
|---|---|
| CMake | Gerenciamento de configuração e construção de projetos |
| Make | Automatização de tarefas de compilação |
| Ninja | Sistema de construção de projetos |
| Git | Controle de versão |
| GDB | Depuração de programas |
| Clang | Compilador e ferramentas LLVM |
| Valgrind | Análise de memória em plataformas compatíveis |

Essas ferramentas serão estudadas em etapas posteriores.

## 16. Exercício prático

Crie um programa que solicite dois números ao usuário e apresente:

1. A soma.
2. A subtração.
3. A multiplicação.
4. A divisão, quando o segundo número for diferente de zero.

### Exemplo de solução

```cpp
#include <iostream>

int main() {
    double numero1;
    double numero2;

    std::cout << "Digite o primeiro numero: ";
    std::cin >> numero1;

    std::cout << "Digite o segundo numero: ";
    std::cin >> numero2;

    std::cout << "\nSoma: "
              << numero1 + numero2 << '\n';

    std::cout << "Subtracao: "
              << numero1 - numero2 << '\n';

    std::cout << "Multiplicacao: "
              << numero1 * numero2 << '\n';

    if (numero2 != 0) {
        std::cout << "Divisao: "
                  << numero1 / numero2 << '\n';
    } else {
        std::cout << "Divisao impossivel: divisor igual a zero.\n";
    }

    return 0;
}
```

### Objetivo do exercício

Praticar:

- Criação de arquivos `.cpp`.
- Escrita de código.
- Utilização do compilador.
- Compilação pelo terminal.
- Execução de programas.
- Entrada e saída de dados.

## 17. Checklist de aprendizagem

Ao concluir este tópico, você deverá saber:

- [ ] O que é um ambiente de desenvolvimento.
- [ ] A diferença entre editor e compilador.
- [ ] Como instalar o Visual Studio Code.
- [ ] Como instalar a extensão C/C++.
- [ ] Como instalar o GCC utilizando MSYS2.
- [ ] Como configurar a variável PATH.
- [ ] Como verificar a instalação do G++.
- [ ] Como criar um arquivo `.cpp`.
- [ ] Como compilar um programa.
- [ ] Como executar um programa pelo PowerShell.
- [ ] Como selecionar um padrão C++ durante a compilação.

## 18. Resumo

Configurar o ambiente de desenvolvimento é uma das primeiras etapas para começar a programar em C++.

Neste tópico, aprendemos a utilizar:

- Visual Studio Code como editor.
- Extensão C/C++ para recursos de programação.
- MSYS2 para instalar ferramentas.
- GCC/G++ como compilador.
- GDB como depurador.
- PowerShell como terminal.

Com essas ferramentas instaladas, já podemos criar, compilar, executar e testar programas C++ no Windows.

## 19. Referências

- [Visual Studio Code](https://code.visualstudio.com/)
- [Documentação C/C++ do VS Code](https://code.visualstudio.com/docs/languages/cpp)
- [Tutorial GCC com MinGW](https://code.visualstudio.com/docs/cpp/config-mingw)
- [MSYS2 — Site oficial](https://www.msys2.org/)
- [MSYS2 — Ambientes](https://www.msys2.org/docs/environments/)
- [GCC — Documentação oficial](https://gcc.gnu.org/onlinedocs/)
- [GDB — Documentação oficial](https://www.sourceware.org/gdb/documentation/)
