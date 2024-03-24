# Tudo sobre Shell Script

- **Shell Script** é uma linguagem de script utilizada principalmente em sistemas **_Unix_** e **_Unix-like_** para **automatizar tarefas** do sistema operacional. Ela é interpretada por um shell, que é a interface de linha de comando do sistema operacional
- O termo "_shell_" refere-se à **interface de linha de comando** de um sistema operacional. O "_script_" refere-se a um conjunto de comandos escritos em um arquivo de texto que são interpretados e executados em sequência pelo shell

## Introdução

Aqui você irá encontrar tudo sobre de Shell Script desde sobre a linguagem à exemplos, boas práticas, nomenclatura de variáveis, execução de arquivos `.sh`, definição de variáveis e convenções de nomes, variáveis especiais, construtores de controle de fluxo, comparações, loops, break e continue, operadores, substituições, arrays, outros tipos de dados, definição e uso de funções, mecanismos de cotação e mais

- O **Shell Script** foi desenvolvido para **facilitar a automação de tarefas repetitivas**, a **manipulação de arquivos**, o **gerenciamento de processos** e a **interação com o sistema operacional** de forma programática
- O conceito de **Shell Script** remonta aos primeiros sistemas **_Unix_**, que foram **desenvolvidos na década de 1960 e 1970** por programadores na **Bell Labs**, como **Ken Thompson**, **Dennis Ritchie**, e outros. Desde então, o Shell Script tem sido uma **parte fundamental dos sistemas _Unix_ e _Unix-like_**, sendo adaptado e aprimorado ao longo do tempo
- Seu objetivo principal é oferecer uma maneira de **automatizar tarefas** do sistema operacional e **facilitar a interação com o ambiente** _Unix-like_ por meio de comandos e scripts. Com Shell Script, os usuários podem criar scripts para realizar uma variedade de tarefas, desde operações simples de manipulação de arquivos até scripts mais complexos de gerenciamento de sistemas

> Nota: O único requisito para ler este "Tudo sobre" é ter uma base em lógica de programação

Tópicos:

- [Tudo sobre Shell Script](#tudo-sobre-shell-script)
  - [Introdução](#introdução)
  - [Como executar um arquivo `.sh`?](#como-executar-um-arquivo-sh)
    - [Reconhecimento automático de arquivos](#reconhecimento-automático-de-arquivos)
  - [Variáveis e convenções de nomes](#variáveis-e-convenções-de-nomes)
    - [Variáveis especiais e de ambiente](#variáveis-especiais-e-de-ambiente)
  - [Operadores](#operadores)
    - [Operadores aritméticos](#operadores-aritméticos)
    - [Operadores relacionais](#operadores-relacionais)
    - [Operadores lógicos](#operadores-lógicos)
    - [Operadores de atribuição](#operadores-de-atribuição)
    - [Outros operadores](#outros-operadores)
  - [Construtores de controle de fluxo](#construtores-de-controle-de-fluxo)
    - [Comparações](#comparações)
      - [Estrutura `case`](#estrutura-case)
    - [Estruturas de repetição](#estruturas-de-repetição)
      - [Estrutura `for`](#estrutura-for)
      - [Estrutura `while`](#estrutura-while)
      - [Estrutura `until`](#estrutura-until)
      - [Controle de fluxo com `break` e `continue`](#controle-de-fluxo-com-break-e-continue)
  - [Tipos de dados](#tipos-de-dados)
    - [Números inteiros](#números-inteiros)
    - [Texto (_Strings_)](#texto-strings)
      - [Acessando caracteres específicos](#acessando-caracteres-específicos)
      - [Mecanismos de cotação](#mecanismos-de-cotação)
    - [Números decimais (_Floats_)](#números-decimais-floats)
    - [_Booleans_](#booleans)
    - [_Arrays_](#arrays)
      - [Declaração](#declaração)
      - [Acessando elementos](#acessando-elementos)
      - [Número de elementos](#número-de-elementos)
      - [Iterando sobre um](#iterando-sobre-um)
      - [Manipulação](#manipulação)
  - [Funções](#funções)
    - [Definindo](#definindo)
    - [Chamando](#chamando)
    - [Passagem de parâmetros](#passagem-de-parâmetros)
    - [Retorno de valores](#retorno-de-valores)
    - [Escopo de variáveis](#escopo-de-variáveis)
    - [Benefícios das funções](#benefícios-das-funções)
  - [Fontes e referências](#fontes-e-referências)

## Como executar um arquivo `.sh`?

Para executar um arquivo Shell Script, siga estes passos simples:

1. Crie um novo arquivo com a extensão `.sh`, por exemplo, `meu_script.sh`
2. Abra o arquivo em um editor de texto e escreva o código Shell Script desejado
3. Salve o arquivo
4. Abra um terminal e navegue até o diretório onde o arquivo `.sh` está localizado
5. Torne o arquivo executável com o comando: `chmod +x meu_script.sh`
6. Execute o script digitando `./meu_script.sh` no terminal e pressionando Enter

### Reconhecimento automático de arquivos

---

Não é estritamente necessário que um arquivo Shell Script tenha a extensão `.sh` no final do nome. Se o arquivo incluir a linha `#!/bin/bash` no topo, o sistema identificará automaticamente como um arquivo Shell Script. Essa linha é conhecida como _shebang_ ou _hashbang_ e especifica o interpretador que será usado para executar o script

A presença do _shebang_ permite que o sistema operacional execute o script no ambiente apropriado. Por exemplo, `#!/bin/bash` indica que o interpretador Bash deve ser utilizado para executar o script. Se for `#!/bin/sh`, o interpretador padrão do sistema será usado

Essa flexibilidade na nomenclatura dos arquivos Shell Script permite uma organização mais intuitiva dos arquivos e facilita a identificação de seu propósito, especialmente em situações onde a extensão do arquivo não pode ser modificada ou não é desejável

É importante observar que, embora a presença do _shebang_ facilite a identificação do interpretador apropriado, os arquivos Shell Script ainda precisam ter permissões de execução para serem executados. Isso pode ser configurado usando o comando `chmod +x nome_do_arquivo.sh` que concede a permissão de execução

## Variáveis e convenções de nomes

Convenções de nomes são diretrizes ou regras estabelecidas para a escolha de nomes de variáveis, funções, arquivos, classes ou outros elementos em um programa de computador. Essas convenções ajudam a padronizar o código-fonte e torná-lo mais legível e compreensível para os programadores  
As convenções de nomes em ShellScript seguem algumas regras básicas:

1. **Letras iniciais**: Os nomes de variáveis devem começar com uma letra (maiúscula ou minúscula) ou um sublinhado (\_)
2. **Caracteres subsequentes**: Após a primeira letra, os nomes de variáveis podem conter letras, dígitos e sublinhados
3. **Sensibilidade a maiúsculas e minúsculas**: Os nomes de variáveis são sensíveis a maiúsculas e minúsculas. Ou seja, uma variável chamada "nome" é diferente de uma variável chamada "Nome"
4. **Palavras reservadas**: Evite utilizar palavras reservadas do Shell como nomes de variáveis. Essas palavras são usadas pela própria linguagem e podem causar comportamentos inesperados se forem sobrescritas
5. **Convenção de nomes**: Embora não seja uma regra estrita, é comum utilizar letras minúsculas para nomes de variáveis em ShellScript. Além disso, para nomes compostos, é comum separar as palavras usando sublinhados (\_), por exemplo: `nome_completo`

Seguindo essas convenções, você pode garantir que seus scripts sejam mais legíveis e fáceis de entender e manter

Aqui está um exemplo de definição de variável:

```sh
nome="Shell Script"
```

### Variáveis especiais e de ambiente

---

Além das variáveis comuns, existem várias **variáveis especiais** disponíveis em Shell Script que fornecem informações úteis sobre a execução do script:

- `$0`: Representa o nome do próprio script
- `$1`, `$2`, etc.: Representam os parâmetros posicionais passados para o script
- `$#`: Indica o número total de parâmetros posicionais
- `$@`: Representa todos os parâmetros posicionais como uma única string
- `$?`: Retorna o código de saída do último comando executado
- `$$`: Fornece o PID (Process ID) do script atual
- `$!`: Retorna o PID do último processo em segundo plano iniciado pelo script

Essas variáveis especiais são muito úteis para **automatizar tarefas** e para a **tomada de decisões** dentro de scripts, permitindo que eles sejam **mais dinâmicos** e adaptem-se às condições de execução  
Além das variáveis especiais mencionadas anteriormente, existem outras **variáveis de ambiente comuns** em Shell Script que fornecem informações úteis sobre o ambiente de execução do script. Aqui estão algumas delas:

- `$HOME`: O diretório home do usuário atual
- `$USER`: O nome do usuário atual
- `$PWD`: O diretório de trabalho atual (presente)
- `$SHELL`: O shell padrão do usuário
- `$PATH`: Uma lista de diretórios onde o sistema procura por programas executáveis
- `$LANG`: Define a configuração de idioma do sistema
- `$HOSTNAME`: O nome do host da máquina
- `$TERM`: O tipo de terminal que está sendo usado
- `$EDITOR`: O editor de texto padrão
- `$DISPLAY`: O display X11 (gráfico) onde os aplicativos devem ser exibidos
- `$TZ`: O fuso horário atual

Essas variáveis de ambiente são frequentemente utilizadas em scripts para **adaptar o comportamento do script** com base no ambiente em que estão sendo executadas. Elas ajudam os scripts a serem mais **portáveis e flexíveis**, permitindo que eles funcionem em **diferentes sistemas** e **ambientes**

## Operadores

Os operadores **aritméticos** realizam **operações matemáticas**. Operadores **relacionais** **comparam valores**. Operadores **lógicos** combinam **expressões lógicas**. Operadores de **atribuição** **atribuem valores** a variáveis e podem realizar operações combinadas. Outros operadores incluem **redirecionamento de entrada e saída**, além de **teste de igualdade e desigualdade**. Todos esses operadores são essenciais para manipular dados e controlar o fluxo de execução em scripts de Shell

### Operadores aritméticos

- `+` : **Soma**
  - Soma dois números
  - Exemplo: `2 + 3` resulta em `5`
- `-` : **Subtração**
  - Subtrai um número de outro
  - Exemplo: `5 - 3` resulta em `2`
- `*` : **Multiplicação**
  - Multiplica dois números
  - Exemplo: `2 * 3` resulta em `6`
- `/` : **Divisão**
  - Divide um número por outro
  - Exemplo: `6 / 2` resulta em `3`
- `%` : **Módulo** (resto da divisão)
  - Retorna o resto da divisão entre dois números
  - Exemplo: `7 % 3` resulta em `1`
- `**` : **Exponenciação**
  - Eleva um número a uma potência
  - Exemplo: `2 ** 3` resulta em `8`

### Operadores relacionais

- `-eq` : **Igual a**
  - Verifica se dois valores são iguais
  - Exemplo: `5 -eq 5` retorna verdadeiro
- `-ne` : **Diferente de**
  - Verifica se dois valores são diferentes
  - Exemplo: `5 -ne 3` retorna verdadeiro
- `-gt` : **Maior que**
  - Verifica se o primeiro valor é maior que o segundo
  - Exemplo: `5 -gt 3` retorna verdadeiro
- `-lt` : **Menor que**
  - Verifica se o primeiro valor é menor que o segundo
  - Exemplo: `3 -lt 5` retorna verdadeiro
- `-ge` : **Maior ou igual a**
  - Verifica se o primeiro valor é maior ou igual ao segundo
  - Exemplo: `5 -ge 5` retorna verdadeiro
- `-le` : **Menor ou igual a**
  - Verifica se o primeiro valor é menor ou igual ao segundo
  - Exemplo: `3 -le 5` retorna verdadeiro

### Operadores lógicos

- `&&` : **E lógico**
  - Combina duas condições onde ambas precisam ser verdadeiras
  - Exemplo: `(2 -eq 2) && (3 -lt 5)` retorna verdadeiro
- `||` : **OU lógico**
  - Combina duas condições onde pelo menos uma precisa ser verdadeira
  - Exemplo: `(2 -eq 3) || (3 -lt 5)` retorna verdadeiro
- `!` : **NÃO lógico**
  - Inverte o resultado de uma condição
  - Exemplo: `!(2 -eq 3)` retorna verdadeiro

### Operadores de atribuição

- `=` : **Atribuição**
  - Atribui um valor a uma variável
  - Exemplo: `x=5`
- `+=` : **Adição e atribuição**
  - Adiciona um valor a uma variável existente
  - Exemplo: `x+=2` onde `x` é 5, resulta em `x` igual a 7
- `-=` : **Subtração e atribuição**
  - Subtrai um valor de uma variável existente
  - Exemplo: `x-=2` onde `x` é 7, resulta em `x` igual a 5
- `*=` : **Multiplicação e atribuição**
  - Multiplica um valor por uma variável existente
  - Exemplo: `x*=2` onde `x` é 5, resulta em `x` igual a 10
- `/=` : **Divisão e atribuição**
  - Divide uma variável existente por um valor
  - Exemplo: `x/=2` onde `x` é 10, resulta em `x` igual a 5

### Outros operadores

- `>` : **Redirecionamento de saída**
  - Redireciona a saída padrão de um comando para um arquivo
  - Exemplo: `ls > lista_arquivos.txt` cria um arquivo `lista_arquivos.txt` com a saída do comando `ls`
- `>>` : **Anexar saída a um arquivo**
  - Anexa a saída padrão de um comando a um arquivo existente
  - Exemplo: `echo "Nova linha" >> arquivo.txt` adiciona "Nova linha" ao final de `arquivo.txt`
- `<` : **Redirecionamento de entrada**
  - Fornece entrada padrão de um arquivo para um comando
  - Exemplo: `cat < arquivo.txt` exibe o conteúdo de `arquivo.txt` no terminal
- `<<` : **Aqui documento (redirecionamento de entrada)**
  - Permite entrada de múltiplas linhas diretamente no terminal
  - Exemplo: `cat << FIM` permite inserir várias linhas de texto até que `FIM` seja digitado
- `&>` : **Redirecionar saída padrão e de erro para o mesmo local**
  - Redireciona tanto a saída padrão quanto a saída de erro de um comando para o mesmo local
  - Exemplo: `ls /arquivo/inexistente &> log.txt` redireciona tanto a saída de erro quanto a saída padrão do comando `ls` para o arquivo `log.txt`

Estes são os operadores fundamentais usados em Shell Script. Eles permitem fazer **cálculos**, **comparar valores**, **controlar o fluxo** de execução e **gerenciar a entrada e saída de dados** nos scripts  
Agora, voltando aos operadores `=` e `!=` eles podem ser usados em vários contextos, principalmente em **estruturas de controle de fluxo**, como `if`, `elif` e `case`, para comparar valores e tomar decisões baseadas nessas comparações

- `=` : **Teste de igualdade (em alguns contextos)**
  - Verifica se dois valores são iguais
  - Exemplo: `[ "{$x}" = "{$y}" ]` verifica se as variáveis `x` e `y` são iguais
- `!=` : **Teste de desigualdade (em alguns contextos)**
  - Verifica se dois valores são diferentes
  - Exemplo: `[ "{$x}" != "{$y}" ]` verifica se as variáveis `x` e `y` são diferentes

Além disso, eles também são frequentemente usados em expressões condicionais em **comandos de teste**, como `[ ]` (ou `test`), para verificar condições  
Por exemplo, em um `if` _statement_:

```sh
if [ "{$x}" = "{$y}" ]; then
    echo "x é igual a y"
fi
```

Neste caso, `$x` e `$y` são variáveis cujos valores estão sendo comparados usando o operador `=`. Se os valores forem iguais, o comando `echo` será executado  
Outro exemplo pode ser no comando de teste `[ ]`:

```sh
if [ "{$x}" != "{$y}" ]; then
    echo "x é diferente de y"
fi
```

Neste caso, estamos verificando se `$x` é diferente de `$y`. Se forem diferentes, o comando `echo` será executado  
Esses são apenas alguns exemplos de como esses operadores podem ser usados em diferentes contextos em Shell Script. Eles são fundamentais para realizar comparações e tomar decisões dentro dos scripts

## Construtores de controle de fluxo

Shell Script oferece uma variedade de construtores de controle de fluxo para realizar decisões e repetições, proporcionando flexibilidade e poder de automação aos scripts

### Comparações

---

A estrutura `if` permite executar um bloco de código com base em uma condição especificada. Em Shell Script, as comparações são realizadas usando comandos de teste `[ ]` ou `[[ ]]`  
Exemplo de comparação numérica:

```sh
if [ $idade -ge 18 ]; then
    echo "Você é maior de idade."
else
    echo "Você é menor de idade."
fi
```

Agora suponha que você queira verificar **múltiplas condições em sequência**. Você pode usar a estrutura `if` para verificar a primeira condição, seguida por uma série de `elif` (que é uma combinação de `else` e `if` em algumas linguagens) para verificar as condições subsequentes, e finalmente um bloco `else` para lidar com qualquer outra condição que não foi satisfeita pelas verificações anteriores  
Aqui está um exemplo de como isso pode ser feito em Shell Script:

```sh
if [ $idade -lt 18 ]; then
    echo "Você é menor de idade."
elif [ $idade -ge 18 ] && [ $idade -lt 65 ]; then
    echo "Você é um adulto."
else
    echo "Você é um idoso."
fi
```

Neste exemplo, o primeiro `if` verifica se a idade é menor que 18. Se não for, ele passa para o próximo `elif` (abreviação de "else if") para verificar se a idade está entre 18 e 65 anos. Se nenhuma dessas condições for verdadeira, o bloco `else` final será executado  
Aqui, o script verifica se a variável `idade` é maior ou igual a 18 e imprime uma mensagem apropriada com base nessa condição

#### Estrutura `case`

---

A estrutura `case` é uma forma eficiente de realizar **múltiplas comparações** em uma única variável e executar um bloco de código correspondente ao padrão que corresponda  
No exemplo abaixo, uma variável chamada `$opcao` é testada em diferentes padrões. Se o valor de `$opcao` corresponder a um dos padrões especificados, o bloco de código correspondente será executado

```sh
case $opcao in
    1)
        echo "Opção 1 selecionada."
        ;;
    2)
        echo "Opção 2 selecionada."
        ;;
    *)
        echo "Opção inválida."
        ;;
esac
```

No exemplo acima:

- Se `$opcao` for igual a 1, o script imprimirá "Opção 1 selecionada."
- Se `$opcao` for igual a 2, o script imprimirá "Opção 2 selecionada."
- Caso contrário, se `$opcao` não corresponder a nenhum dos padrões especificados, o script imprimirá "Opção inválida."

A estrutura `case` é especialmente útil quando há **várias opções a serem consideradas** e simplifica o código em comparação com múltiplos `if` e `elif`. Ela é amplamente utilizada em scripts de Shell Script para lidar com várias condições de forma clara e concisa  
Neste exemplo, o script executa um bloco de código dependendo do valor da variável `opcao`

### Estruturas de repetição

As estruturas de repetição em Shell Script são fundamentais para executar blocos de código **repetidamente** com base em certas **condições** ou **iterações**. Aqui estão os principais construtores de repetição em Shell Script:

#### Estrutura `for`

---

A estrutura `for` permite iterar sobre uma **lista de valores** especificados, executando um bloco de código para cada item na lista  
Exemplo:

```sh
for cor in vermelho amarelo azul; do
    echo "A cor é: $cor"
done
```

Neste exemplo simples, o script itera sobre uma lista de cores e imprime cada uma delas

#### Estrutura `while`

---

A estrutura `while` permite executar um bloco de código repetidamente enquanto uma **condição** especificada **for verdadeira**  
Exemplo:

```sh
contador=0
while [ $contador -lt 5 ]; do
    echo "Contador: $contador"
    contador=$((contador + 1))
done
```

Este trecho de código imprime o valor do contador enquanto ele for menor que 5

#### Estrutura `until`

---

A estrutura `until` é semelhante ao `while`, mas executa um bloco de código repetidamente até que uma **condição** especificada **seja verdadeira**  
Exemplo:

```sh
contador=0
until [ $contador -eq 5 ]; do
    echo "Contador: $contador"
    contador=$((contador + 1))
done
```

Neste caso, o script continua a imprimir o valor do contador até que ele seja igual a 5  
Essas estruturas de repetição são essenciais para automatizar tarefas repetitivas e criar scripts Shell Script eficazes. Elas oferecem grande poder e flexibilidade na automação de processos e são amplamente utilizadas em scripts de gerenciamento de sistemas e automação de tarefas

#### Controle de fluxo com `break` e `continue`

---

Em Shell Script, os comandos `break` e `continue` são ferramentas valiosas para controlar o fluxo de loops, permitindo maior flexibilidade e eficiência na execução de scripts  
O comando `break` é utilizado para **sair** imediatamente de um loop quando uma determinada condição é atendida. No exemplo abaixo, o loop `for` itera sobre os números de 1 a 5, mas quando o valor de `i` é igual a 3, o comando `break` é acionado, encerrando o loop prematuramente:

```sh
for i in 1 2 3 4 5; do
    if [ $i -eq 3 ]; then
        break
    fi
    echo $i
done
```

O resultado será a impressão dos números 1 e 2, seguido pelo término do loop quando `i` é 3  
Por outro lado, o comando `continue` é utilizado para **pular** a iteração atual de um loop e continuar com a próxima iteração. No exemplo a seguir, quando `i` é igual a 3, o comando `continue` é acionado, fazendo com que a iteração seja interrompida e o loop prossiga para o próximo valor de `i`:

```sh
for i in 1 2 3 4 5; do
    if [ $i -eq 3 ]; then
        continue
    fi
    echo $i
done
```

Neste caso, o número 3 não será impresso, mas os demais números serão, resultando na impressão de 1, 2, 4 e 5  
O uso combinado desses comandos oferece um controle preciso sobre a execução de loops em Shell Script, permitindo lidar com situações específicas de forma **eficiente e elegante**

Claro, vou explicar de forma mais detalhada sobre os tipos de dados em Shell Script:

## Tipos de dados

Os tipos de dados em Shell Script são formas de categorizar e organizar as informações que o programa manipula. Cada tipo de dado tem características específicas e pode ser utilizado para diferentes propósitos

### Números inteiros

---

Os números inteiros são usados para representar **valores numéricos sem frações**. Eles podem ser **positivos** (como 1, 2, 3) ou **negativos** (como -1, -2, -3)  
Exemplo:

```bash
idade=10
```

Neste exemplo, `idade` é uma variável que armazena o número inteiro 10

### Texto (_Strings_)

---

As strings são sequências de caracteres, como **letras, números e símbolos**. Elas são usadas para representar **texto ou palavras**  
Exemplo:

```bash
nome="João"
```

Aqui, `nome` é uma variável que armazena o texto "João"

#### Acessando caracteres específicos

---

Para acessar caracteres específicos dentro de uma string armazenada em um elemento de array, você pode usar a mesma sintaxe usada para strings simples  
Exemplo:

```bash
palavra="Shell"
echo ${palavra:1:3}  # Saída: hel (retorna os caracteres da posição 1 à 3)
```

#### Mecanismos de cotação

---

Os mecanismos de cotação referem-se à forma como você delimita strings ou expressões para que o interpretador de shell as processe de maneira específica. Existem três tipos principais de cotações em shell script:

1. **Aspas Simples (' '):** Quando você envolve uma string entre aspas simples, o conteúdo é interpretado literalmente. Nenhuma expansão de variável ou caracteres especiais dentro da string é realizada. Por exemplo:

   ```bash
   echo 'Olá, $USER'  # Saída será: Olá, $USER
   ```

2. **Aspas Duplas (" "):** As aspas duplas permitem a expansão de variáveis dentro da string. Além disso, certos caracteres especiais são interpretados de forma especial (por exemplo, `\n` é interpretado como uma nova linha). Por exemplo:

   ```bash
   echo "Olá, $USER"  # Saída será: Olá, [nome do usuário atual]
   ```

3. **Cotação entre Acentos Grave (\` \`):** Também conhecida como acentos invertidos ou backticks, isso permite que você execute comandos dentro da string e use a saída desse comando. Por exemplo:

   ```bash
   files=`ls`
   echo "Arquivos no diretório atual: $files"
   ```

Aqui, o comando `ls` é executado e a saída é atribuída à variável `files`

Cada tipo de cotação tem seu propósito específico e é importante escolher o tipo certo dependendo do que você deseja realizar no seu script

### Números decimais (_Floats_)

---

Os números decimais, ou floats, são usados quando precisamos de valores com **parte fracionária**, como 3.14 ou -0.5  
Exemplo:

```bash
preco=3.99
```

Neste exemplo, `preco` é uma variável que armazena o número decimal 3.99

### _Booleans_

---

Os booleans são tipos de dados que podem ter apenas dois valores: **verdadeiro** ou **falso**. Eles são usados para representar condições
Exemplo:

```bash
esta_chovendo=true
usuario_logado=false
```

Aqui, `esta_chovendo` é uma variável booleana que indica se está chovendo ou não  
E `usuario_logado` indica se um usuário está logado no sistema

### _Arrays_

---

Os arrays são estruturas de dados que permitem armazenar múltiplos valores em uma única variável. Cada valor em um array é identificado por um índice, que começa em 0 para o primeiro elemento

#### Declaração

Você pode declarar um array atribuindo uma lista de valores entre parênteses para uma variável  
Exemplo:

```bash
nomes=("Maria" "João" "Ana")
```

---

#### Acessando elementos

Você pode acessar elementos individuais de um array usando o índice correspondente entre colchetes  
Exemplo:

```bash
echo ${nomes[0]}  # Saída: Maria
echo ${nomes[1]}  # Saída: João
echo ${nomes[2]}  # Saída: Ana
```

---

#### Número de elementos

Você pode obter o número de elementos em um array usando `${#array[@]}`  
Exemplo:

```bash
echo ${#nomes[@]}  # Saída: 3 (número de elementos em 'nomes')
```

---

#### Iterando sobre um

Você pode percorrer os elementos de um array usando uma estrutura de repetição, como `for` loop  
Exemplo:

```bash
nomes=("Maria" "João" "Ana")
for nome in "${nomes[@]}"; do
    echo "Nome: $nome"
done
```

Este loop `for` itera sobre cada elemento do array `nomes` e imprime o nome correspondente

---

#### Manipulação

Você pode adicionar elementos a um array usando a sintaxe de atribuição e índice  
Exemplo:

```bash
nomes=()  # Cria um array vazio
nomes[0]="Maria"
nomes[1]="João"
nomes[2]="Ana"
```

Você também pode remover elementos de um array usando o comando `unset`  
Exemplo:

```bash
unset nomes[1]  # Remove o segundo elemento do array 'nomes'
```

Os arrays são uma ferramenta poderosa em Shell Script, permitindo a manipulação de conjuntos de dados de forma eficiente. Com eles, você pode armazenar e acessar facilmente uma coleção de valores e realizar diversas operações em conjunto, tornando a programação em Shell Script mais flexível e poderosa

## Funções

As funções em Shell Script são **blocos de código** que podem ser definidos uma vez e chamados várias vezes para executar uma tarefa específica. Elas são extremamente úteis para organizar e reutilizar o código, tornando-o mais modular e fácil de entender

### Definindo

---

Para definir uma função, você usa a seguinte sintaxe:

```bash
nome_da_funcao() {
    # Corpo da função
}
```

Por exemplo:

```bash
minha_funcao() {
    echo "Olá, $1!"
}
```

Neste exemplo, `minha_funcao` é o nome da função e `echo "Olá, $1!"` é o corpo da função. O `$1` representa o primeiro argumento passado para a função

### Chamando

---

Para chamar uma função, basta usar seu nome seguido pelos parâmetros (se definidos)

```bash
minha_funcao "João"
```

### Passagem de parâmetros

---

Você pode passar argumentos para funções da mesma forma que passa argumentos para scripts. Os parâmetros são acessíveis dentro da função através de `$1`, `$2`, etc.

Para definir parâmetros em uma função, você pode usar variáveis posicionais. Esses parâmetros são passados para a função quando ela é chamada e podem ser acessados dentro da função usando variáveis especiais, como `$1`, `$2`, `$3` e assim por diante, onde `$1` representa o primeiro parâmetro, `$2` o segundo e assim por diante  
Aqui está um exemplo de como definir parâmetros em uma função:

```bash
minha_funcao() {
    echo "Olá, $1! Bem-vindo ao mundo de Shell Script."
}

# Chamando a função com um parâmetro
minha_funcao "João"
```

Neste exemplo, a função `minha_funcao` tem um parâmetro `$1`, que é acessado dentro da função para exibir uma saudação personalizada. Quando a função é chamada com `"João"` como argumento, ele é passado para `$1`, e a saída será "Olá, João! Bem-vindo ao mundo de Shell Script."

Você também pode definir e acessar múltiplos parâmetros em uma função, da mesma forma que `$1`, `$2`, etc., representam o primeiro, segundo, etc., parâmetros passados para a função

```bash
outra_funcao() {
    echo "Olá, $1 e $2! Bem-vindos ao mundo de Shell Script."
}

# Chamando a função com dois parâmetros
outra_funcao "Maria" "João"
```

Neste exemplo, a função `outra_funcao` tem dois parâmetros `$1` e `$2`, que são usados para exibir uma saudação personalizada para dois nomes. Quando a função é chamada com `"Maria"` e `"João"` como argumentos, eles são passados para `$1` e `$2` respectivamente, e a saída será "Olá, Maria e João! Bem-vindos ao mundo de Shell Script."

### Retorno de valores

---

Shell Script não suporta explicitamente o retorno de valores de funções como em outras linguagens de programação. No entanto, você pode usar a saída padrão (`echo`) para retornar valores

### Escopo de variáveis

---

As variáveis definidas dentro de uma função têm **escopo local**, o que significa que elas **não são visíveis fora da função**, a menos que sejam explicitamente declaradas como globais  
Uma variável definia normalmente já tem o escopo local, agora para definir uma **variável explicitamente como global**, você pode usar a palavra-chave `declare` com a opção `-g`. Isso garante que a variável seja tratada como global e possa ser acessada dentro e fora da função  
Aqui está um exemplo de como definir uma variável como global dentro de uma função:

```bash
minha_funcao() {
    declare -g variavel_global="Esta é uma variável global"
    echo "Dentro da função: $variavel_global"
}

# Chamando a função
minha_funcao

# Acessando a variável global fora da função
echo "Fora da função: $variavel_global"
```

Neste exemplo, a função `minha_funcao` define a variável `variavel_global` como global usando `declare -g`. Dentro da função, ela imprime o valor dessa variável. Fora da função, a mesma variável é acessada e seu valor é impresso novamente

Lembre-se de que, ao usar variáveis globais, você deve ter cuidado para não alterar seus valores acidentalmente em partes do código onde não é desejado. O uso de variáveis globais deve ser feito com moderação e preferencialmente evitado quando possível para manter o código mais legível e fácil de entender

Um pequeno exemplo:

```bash
# Define a função
minha_funcao() {
    echo "Olá, $1!"
}

# Chama a função
minha_funcao "João"
```

### Benefícios das funções

---

- **Reutilização de Código:** Você pode definir uma função uma vez e usá-la várias vezes em seu script
- **Organização do Código:** Funções permitem dividir o código em partes menores e mais gerenciáveis, facilitando a manutenção
- **Legibilidade:** Ao atribuir tarefas específicas a funções com nomes descritivos, o código se torna mais fácil de entender e depurar

## Fontes e referências

Aqui estão algumas fontes valiosas que podem enriquecer sua jornada de aprendizado:

1. **Documentação Oficial do Bash**: Para um entendimento sólido dos fundamentos e funcionalidades avançadas do Bash, o interpretador de comandos shell mais comum, a documentação oficial é uma fonte indispensável. Ela pode ser encontrada no site GNU: [Documentação Oficial do Bash](https://www.gnu.org/software/bash/manual/)

2. **Tutoriais Online**: A internet oferece uma ampla gama de tutoriais para ajudá-lo a dominar o Shell Script. Alguns sites populares incluem:
   - **[Linuxize](https://linuxize.com/)**: Oferece tutoriais e guias detalhados sobre Shell Script
   - **[Shell Scripting Tutorial](https://www.shellscript.sh/)**: Um tutorial abrangente com exemplos e exercícios práticos para aprender Shell Script
   - [**Shell Scripting Tutorial - Tutorialspoint**](https://www.tutorialspoint.com/unix/shell_scripting.htm): Este tutorial abrangente oferece uma introdução passo a passo ao Shell Scripting, cobrindo desde conceitos básicos até técnicas avançadas

3. **Fóruns e Comunidades Online**: Participar de fóruns e comunidades é uma excelente maneira de obter suporte e compartilhar conhecimentos com outros entusiastas de Shell Script. Alguns espaços populares incluem:
   - **[Unix & Linux Stack Exchange](https://unix.stackexchange.com/)**: Uma comunidade de perguntas e respostas que aborda sistemas Unix e Linux
   - **[Reddit - r/bash](https://www.reddit.com/r/bash/)**: Um subreddit dedicado a discussões sobre Bash e Shell Script

É importante ressaltar que o Shell Script é uma área vasta e em constante evolução. Portanto, explorar diversas fontes é essencial para obter uma compreensão completa e atualizada desse campo dinâmico
