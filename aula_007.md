
# Editores de Código e Ambientes de Desenvolvimento Integrados

## 1. Introdução

Para desenvolver programas em C++, precisamos de um ambiente onde possamos escrever, organizar, compilar, executar e depurar nosso código.

Existem ferramentas específicas para essas tarefas, conhecidas como **Code Editors (Editores de Código)** e **IDEs (Integrated Development Environments)**.

Essas ferramentas facilitam o desenvolvimento de software, oferecendo recursos que ajudam os programadores a escrever códigos com mais produtividade, organização e segurança.

Algumas das ferramentas mais conhecidas para desenvolvimento C++ são:

- Visual Studio Code.
- Visual Studio.
- CLion.
- Code::Blocks.
- Qt Creator.
- Eclipse CDT.
- Neovim.

## 2. O que é um Code Editor?

Um **Code Editor** é um editor de texto desenvolvido especialmente para escrever e modificar código-fonte.

Diferentemente de editores de texto comuns, como o Bloco de Notas, os editores de código oferecem funcionalidades específicas para programação.

Entre os recursos mais comuns estão:

- Syntax Highlighting.
- Autocomplete.
- Code Formatting.
- Code Navigation.
- Error Detection.
- Extensões e plugins.

### 2.1 Syntax Highlighting

Syntax Highlighting, ou realce de sintaxe, é um recurso que utiliza diferentes cores para identificar elementos do código.

Exemplo:

```cpp
#include <iostream>

int main() {
    int idade = 20;

    std::cout << "Minha idade: " << idade << std::endl;

    return 0;
}
```

O editor pode utilizar cores diferentes para destacar:

- Palavras-chave.
- Tipos de dados.
- Variáveis.
- Funções.
- Strings.
- Comentários.

Esse recurso facilita a leitura e a identificação de diferentes elementos do programa.

### 2.2 Autocomplete

Autocomplete, também conhecido como preenchimento automático, sugere palavras, funções, variáveis e outros elementos enquanto escrevemos código.

Exemplo:

```cpp
#include <iostream>

int main() {
    std::co
}
```

O editor pode sugerir:

```cpp
std::cout
std::copy
std::cos
```

Isso ajuda a escrever código mais rapidamente e reduz erros de digitação.

### 2.3 Code Formatting

Code Formatting é o recurso responsável por organizar automaticamente a aparência do código.

Exemplo sem formatação:

```cpp
#include <iostream>
int main(){int numero=10;if(numero>5){std::cout<<"Maior";}}
```

Exemplo formatado:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    if (numero > 5) {
        std::cout << "Maior";
    }

    return 0;
}
```

A formatação facilita a leitura e a manutenção do código.

### 2.4 Code Navigation

Code Navigation permite navegar rapidamente entre diferentes partes do projeto.

Por exemplo:

- Ir até a definição de uma função.
- Localizar uma variável.
- Encontrar referências a uma classe.
- Navegar entre arquivos.
- Consultar declarações e implementações.

Esse recurso é especialmente importante em projetos grandes.

### 2.5 Error Detection

Alguns editores conseguem identificar possíveis problemas no código enquanto estamos programando.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = "texto";

    return 0;
}
```

O editor pode indicar que existe uma incompatibilidade entre o tipo `int` e uma string.

A detecção de erros depende da configuração do editor, do compilador e das ferramentas de análise utilizadas.

## 3. O que é uma IDE?

IDE significa **Integrated Development Environment**, ou Ambiente de Desenvolvimento Integrado.

Uma IDE reúne várias ferramentas necessárias para desenvolver software em uma única aplicação.

Normalmente, uma IDE oferece:

- Editor de código.
- Integração com compiladores.
- Sistema de construção (Build System).
- Depurador (Debugger).
- Gerenciamento de projetos.
- Navegação entre arquivos.
- Ferramentas de análise de código.

Uma IDE permite trabalhar em praticamente todas as etapas do desenvolvimento sem precisar alternar constantemente entre diferentes aplicações.

## 4. Diferença entre Code Editor e IDE

Embora os dois sejam utilizados para programar, existem diferenças importantes.

| Característica | Code Editor | IDE |
|---|---|---|
| Edição de código | Sim | Sim |
| Syntax Highlighting | Sim | Sim |
| Autocomplete | Geralmente | Sim |
| Compilador integrado | Depende da configuração | Geralmente integrado |
| Debugger | Depende da configuração | Geralmente integrado |
| Gerenciamento de projetos | Básico ou por extensões | Mais completo |
| Sistema de construção | Configurável | Geralmente integrado |
| Extensibilidade | Geralmente alta | Depende da ferramenta |

### Exemplo de Code Editor

O Visual Studio Code é um editor de código que pode ser transformado em um ambiente bastante completo por meio de extensões e configurações.

### Exemplo de IDE

O Visual Studio é uma IDE completa que oferece editor, compilação, depuração e gerenciamento de projetos integrados.

**Importante:** a diferença entre editores e IDEs nem sempre é absoluta. Algumas ferramentas podem oferecer características dos dois modelos.

## 5. Principais Code Editors e IDEs para C++

### 5.1 Visual Studio Code (VS Code)

O Visual Studio Code é um editor de código gratuito desenvolvido pela Microsoft.

É uma ferramenta bastante popular entre desenvolvedores de diferentes linguagens.

![Visual Studio Code](https://code.visualstudio.com/assets/images/code-stable.png)

Principais características:

- Gratuito.
- Disponível para Windows, Linux e macOS.
- Suporte a extensões.
- IntelliSense.
- Syntax Highlighting.
- Integração com Git.
- Terminal integrado.
- Integração com depuradores.

Para desenvolver em C++, podemos instalar a extensão C/C++ da Microsoft.

Também precisamos configurar um compilador, como GCC ou Clang, e um depurador compatível.

**Vantagens:**

- Leve em comparação com algumas IDEs completas.
- Grande quantidade de extensões.
- Interface personalizável.
- Suporte a diversas linguagens.
- Comunidade bastante ativa.

**Desvantagens:**

- Precisa de configuração adicional para C++.
- Algumas funcionalidades dependem de extensões.
- A configuração de projetos grandes pode exigir ferramentas adicionais.

Site oficial:

https://code.visualstudio.com/

### 5.2 Visual Studio

O Visual Studio é uma IDE desenvolvida pela Microsoft.

É uma ferramenta bastante utilizada para desenvolvimento C++ no Windows.

Principais características:

- Compilador MSVC.
- Depurador integrado.
- Gerenciamento de projetos.
- IntelliSense.
- Integração com CMake.
- Ferramentas de análise de código.
- Suporte a aplicações Windows.

**Vantagens:**

- Ambiente completo.
- Excelente integração com o Windows.
- Depurador avançado.
- Ferramentas integradas para projetos C++.
- Suporte ao compilador MSVC.

**Desvantagens:**

- Pode consumir bastante memória.
- Instalação relativamente grande.
- Algumas funcionalidades dependem da edição utilizada.

Site oficial:

https://visualstudio.microsoft.com/

### 5.3 CLion

O CLion é uma IDE desenvolvida pela JetBrains, voltada principalmente para C e C++.

Principais características:

- IntelliSense avançado.
- Refatoração de código.
- Depurador integrado.
- Integração com CMake.
- Navegação inteligente.
- Análise estática de código.

**Vantagens:**

- Recursos avançados para C++.
- Excelente navegação entre arquivos.
- Ferramentas de refatoração.
- Integração com diferentes compiladores.

**Desvantagens:**

- É uma ferramenta comercial, com condições de acesso que variam conforme a licença.
- Pode consumir bastante memória.
- Pode exigir configuração de toolchains.

Site oficial:

https://www.jetbrains.com/clion/

### 5.4 Code::Blocks

Code::Blocks é uma IDE gratuita e de código aberto voltada para desenvolvimento em C, C++ e Fortran.

Principais características:

- Editor de código.
- Gerenciamento de projetos.
- Integração com compiladores.
- Depurador.
- Sistema de plugins.

**Vantagens:**

- Gratuito.
- Relativamente simples.
- Adequado para projetos de aprendizado.
- Pode ser instalado com uma distribuição que inclui MinGW.

**Desvantagens:**

- Interface menos moderna.
- Menos recursos avançados que algumas IDEs atuais.
- Desenvolvimento e atualização menos ativos que os de outras ferramentas populares.

Site oficial:

https://www.codeblocks.org/

### 5.5 Qt Creator

Qt Creator é uma IDE utilizada principalmente para desenvolver aplicações com o framework Qt.

Também pode ser utilizada para projetos C++ que não dependem do Qt.

Principais características:

- Editor de código.
- Integração com CMake.
- Depuração.
- Navegação de código.
- Ferramentas para interfaces gráficas.
- Integração com compiladores.

**Vantagens:**

- Excelente integração com Qt.
- Ferramentas para interfaces gráficas.
- Suporte a diferentes plataformas.
- Recursos úteis para projetos C++.

**Desvantagens:**

- Algumas funcionalidades são mais voltadas ao ecossistema Qt.
- Pode exigir configuração inicial de compiladores e kits de desenvolvimento.

Site oficial:

https://www.qt.io/product/development-tools

### 5.6 Eclipse CDT

Eclipse CDT é um conjunto de ferramentas que adiciona suporte ao desenvolvimento em C e C++ ao ambiente Eclipse.

Principais características:

- Editor de código.
- Navegação de código.
- Integração com compiladores.
- Depuração.
- Gerenciamento de projetos.

**Vantagens:**

- Gratuito.
- Extensível.
- Suporte a diferentes plataformas.
- Recursos de desenvolvimento C++.

**Desvantagens:**

- Pode consumir bastante memória.
- Configuração pode ser complexa para iniciantes.
- Interface e experiência podem parecer menos simples que as de alternativas modernas.

Site oficial:

https://eclipseide.org/

### 5.7 Neovim

Neovim é um editor de texto extensível, baseado no Vim, muito utilizado por desenvolvedores que preferem trabalhar pelo teclado e configurar seu próprio ambiente.

Principais características:

- Edição baseada em comandos.
- Extensibilidade por plugins.
- Configuração personalizada.
- Integração com ferramentas de desenvolvimento.
- Suporte a LSP (Language Server Protocol).

**Vantagens:**

- Leve.
- Altamente personalizável.
- Grande controle sobre o ambiente.
- Pode oferecer uma experiência de edição bastante rápida.

**Desvantagens:**

- Curva de aprendizado elevada.
- Exige configuração de plugins e ferramentas.
- Não oferece todos os recursos de uma IDE completa por padrão.

Site oficial:

https://neovim.io/

## 6. Comparação entre as principais ferramentas

| Ferramenta | Tipo | Gratuita? | Plataforma |
|---|---|---|---|
| VS Code | Editor extensível | Sim | Windows, Linux e macOS |
| Visual Studio | IDE | Community gratuita, com condições | Windows e macOS |
| CLion | IDE | Licença comercial e opções específicas de acesso | Windows, Linux e macOS |
| Code::Blocks | IDE | Sim | Windows, Linux e macOS |
| Qt Creator | IDE | Possui opções gratuitas e comerciais | Windows, Linux e macOS |
| Eclipse CDT | IDE extensível | Sim | Windows, Linux e macOS |
| Neovim | Editor extensível | Sim | Windows, Linux e macOS |

## 7. O que é IntelliSense?

IntelliSense é um conjunto de recursos de assistência à programação que fornece sugestões e informações enquanto escrevemos código.

No desenvolvimento C++, ele pode oferecer:

- Autocompletar funções e variáveis.
- Informações sobre parâmetros.
- Navegação para definições.
- Identificação de erros.
- Sugestões de código.

Exemplo:

```cpp
#include <iostream>

int main() {
    std::string nome = "Carlos";

    std::cout << nome;

    return 0;
}
```

Ao escrever `std::`, o editor pode apresentar sugestões de elementos disponíveis no namespace `std`.

No VS Code, os recursos de IntelliSense para C++ são fornecidos principalmente pela extensão C/C++ da Microsoft ou por outras ferramentas compatíveis.

## 8. O que é um Debugger?

Debugger, ou depurador, é uma ferramenta que permite acompanhar a execução de um programa para identificar e corrigir problemas.

Com um depurador, podemos:

- Executar o programa passo a passo.
- Criar breakpoints.
- Observar variáveis.
- Analisar a pilha de chamadas.
- Identificar onde um problema acontece.

### 8.1 Breakpoints

Um breakpoint é um ponto definido pelo programador onde a execução do programa será temporariamente interrompida durante a depuração.

Exemplo:

```cpp
#include <iostream>

int main() {
    int numero = 10;

    int dobro = numero * 2;

    std::cout << dobro << std::endl;

    return 0;
}
```

Podemos colocar um breakpoint na linha:

```cpp
int dobro = numero * 2;
```

Quando o programa chegar a essa linha, o depurador interromperá a execução, permitindo analisar o valor de `numero`.

### 8.2 Step Over

Executa a próxima linha sem entrar no interior de uma função chamada por ela.

### 8.3 Step Into

Entra no interior de uma função para acompanhar sua execução.

### 8.4 Step Out

Continua a execução até sair da função atual.

Esses recursos ajudam a entender o comportamento do programa.

## 9. O que é um Language Server?

Um Language Server é um programa que fornece recursos inteligentes de desenvolvimento para um editor de código.

Ele utiliza o protocolo chamado **Language Server Protocol (LSP)** para se comunicar com editores e IDEs.

Entre os recursos oferecidos estão:

- Autocomplete.
- Navegação de código.
- Diagnósticos.
- Informações sobre funções.
- Renomeação de símbolos.
- Busca de referências.

Para C++, uma ferramenta conhecida é o clangd.

Site oficial:

https://clangd.llvm.org/

## 10. Como escolher um editor ou IDE para C++?

A escolha depende do seu nível de experiência, do tipo de projeto e dos recursos necessários.

| Situação | Ferramenta recomendada |
|---|---|
| Aprender os fundamentos de C++ | VS Code ou Code::Blocks |
| Desenvolvimento no Windows | Visual Studio |
| Projetos profissionais em C++ | Visual Studio ou CLion |
| Desenvolvimento com Qt | Qt Creator |
| Ambiente altamente personalizável | Neovim |
| Desenvolvimento multiplataforma | VS Code, CLion ou Qt Creator |

### Para iniciantes

O Visual Studio Code é uma boa escolha porque:

- É gratuito.
- Possui uma interface simples.
- Funciona em diferentes sistemas operacionais.
- Suporta extensões.
- Permite utilizar GCC, Clang e outros compiladores.

Entretanto, quem deseja uma experiência mais integrada no Windows pode começar com o Visual Studio Community.

## 11. Configurando o VS Code para C++

Para desenvolver em C++ com VS Code, precisamos de algumas ferramentas.

### Ferramentas necessárias

1. Visual Studio Code.
2. Extensão C/C++.
3. Compilador GCC, Clang ou MSVC.
4. Depurador compatível, como GDB ou LLDB.

### Passo 1 — Instalar a extensão

Abra o VS Code e acesse Extensions.

Pesquise:

```text
C/C++
```

Instale a extensão publicada pela Microsoft.

### Passo 2 — Verificar o compilador

Abra o terminal integrado e execute:

```powershell
g++ --version
```

Se o comando funcionar, o compilador GCC está disponível.

### Passo 3 — Criar um arquivo C++

Crie um arquivo chamado:

```text
main.cpp
```

Adicione:

```cpp
#include <iostream>

int main() {
    std::cout << "Meu ambiente C++ está funcionando!" << std::endl;

    return 0;
}
```

### Passo 4 — Compilar o programa

No terminal, execute:

```powershell
g++ -std=c++20 main.cpp -o programa.exe
```

### Passo 5 — Executar

```powershell
.\programa.exe
```

Resultado esperado:

```text
Meu ambiente C++ está funcionando!
```

## 12. Boas práticas ao utilizar editores e IDEs

Algumas práticas ajudam a manter o ambiente de desenvolvimento organizado:

1. Utilize nomes claros para arquivos e pastas.
2. Organize os arquivos por responsabilidade.
3. Utilize ferramentas de formatação.
4. Ative a identificação de erros.
5. Aprenda a utilizar o depurador.
6. Mantenha as extensões atualizadas.
7. Utilize controle de versão com Git.
8. Aprenda os atalhos do editor.
9. Configure corretamente o compilador.
10. Evite instalar extensões desnecessárias.

## 13. Exercício prático

Crie um pequeno projeto chamado `editor-test`.

Dentro dele, crie um arquivo `main.cpp`.

Escreva o seguinte programa:

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

    std::cout << "\nInformacoes cadastradas\n";

    std::cout << "Nome: " << nome << std::endl;
    std::cout << "Idade: " << idade << std::endl;

    return 0;
}
```

### Objetivos do exercício

1. Criar um projeto no editor escolhido.
2. Escrever o código.
3. Utilizar o recurso de autocomplete.
4. Formatar o código.
5. Compilar o programa.
6. Executar o programa.
7. Criar um breakpoint.
8. Utilizar o depurador para acompanhar a execução.

## 14. Resumo

Code Editors e IDEs são ferramentas fundamentais para o desenvolvimento de software.

Um Code Editor é voltado principalmente à edição de código, enquanto uma IDE reúne diferentes ferramentas de desenvolvimento em um único ambiente.

Principais conceitos estudados:

- **Code Editor:** editor especializado em código-fonte.
- **IDE:** ambiente integrado de desenvolvimento.
- **Syntax Highlighting:** realce de sintaxe.
- **Autocomplete:** preenchimento automático.
- **Code Formatting:** formatação de código.
- **IntelliSense:** assistência inteligente à programação.
- **Debugger:** ferramenta de depuração.
- **Breakpoint:** ponto de interrupção.
- **Language Server:** serviço que fornece recursos inteligentes ao editor.

Para começar a desenvolver em C++, podemos utilizar o Visual Studio Code com a extensão C/C++ e um compilador como GCC.

## 15. Referências

- [Visual Studio Code](https://code.visualstudio.com/)
- [Visual Studio](https://visualstudio.microsoft.com/)
- [CLion](https://www.jetbrains.com/clion/)
- [Code::Blocks](https://www.codeblocks.org/)
- [Qt Creator](https://www.qt.io/product/development-tools)
- [Eclipse CDT](https://eclipseide.org/)
- [Neovim](https://neovim.io/)
- [clangd](https://clangd.llvm.org/)
- [Microsoft C++ Documentation](https://learn.microsoft.com/en-us/cpp/)
- [C++ Reference](https://en.cppreference.com/w/)
