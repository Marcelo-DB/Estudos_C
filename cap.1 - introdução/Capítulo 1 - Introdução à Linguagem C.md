# Introdução à Linguagem de Programação C

## **📌 Introdução**

🎯 C é uma linguagem de programação compilada, de propósito geral, estruturada, imperativa e procedural, padronizada pela Organização Internacional para Padronização (ISO).

Mas o que isso significa na prática? 🤔


📌 Características da Linguagem C

✅ Linguagem de Programação Compilada de Propósito Geral

* O código-fonte é convertido em código de máquina por um compilador antes da execução.

* Alta performance e eficiência, ideal para sistemas embarcados, SOs e softwares de alto desempenho.


✅ Linguagem Estruturada

* O código é organizado em blocos lógicos, melhorando a legibilidade e manutenção.

* Usa funções para modularizar o código e evitar repetições.


✅ Linguagem Imperativa

* O programa é executado passo a passo, com comandos específicos que dizem ao computador o que fazer e como fazer.

* Usa variáveis, loops e controle de fluxo para manipular o estado do programa.


✅ Linguagem Procedural

* Baseada no conceito de procedimentos (funções) que recebem dados, processam e retornam resultados.

* Foca na execução de algoritmos bem definidos e evita efeitos colaterais inesperados.


✅ Padronizada pelo ISO (C99, C11, C17, etc.)

* A linguagem C segue normas internacionais para garantir compatibilidade e estabilidade.

* C99 trouxe melhorias como declarações mistas, novos tipos de dados (long long, _Bool) e controle de precisão matemática.

C11 e C17 adicionaram mais refinamentos, segurança e suporte para concorrência e threads.


⚠️ Todas essas características serão analisadas cuidadosamente em capítulos posteriores como a estruturação da linguagem, funções 

(procedural), variáveis, loops, controle e fluxo (capítulos 2, 3 e 4), dentre outros, não há a necessidade de se preocupar com tais 

conceitos formais, por enquanto serve como introdução.

## 📌 **Como tudo começou...**


🌕 🧑🏻‍🚀 ☮️ 🚀 O homem tinha acabado de pisar na Lua, os direitos civis estavam em alta pipocando no mundo todo, uma geração de muita 

efervescência social e cultural e a tecnologia não ficou imune a tanta criatividade, ousadia e desenvoltura! Nesse contexto, a 

linguagem C estava sendo criada entre 1969 e 1973 por Dennis Ritchie em colaboração de outros desenvolvedores das linguagens B e 

BCPL o qual C se baseou:

* BCPL - Desenvolvida por Martin Richards em 1967 como uma linguagem de desenvolvimento de compiladores e sistemas operacionais.

* B - Modelada por Ken Thompson que se inspirou muito da linguagem BCPL para criar as primeiras versões do sistema operacional UNIX.

Até então, os sistemas operacionais eram programas em *linguagens de baixo nível* como Assembly e isso tornava muito complexo o 

desenvolvimento e a manutenção desses sistemas por parte dos programadores.


```assembly

section .data
    msg db "Hello, World!", 0xA  ; Mensagem a ser impressa, com newline (\n)
    len equ $ - msg              ; Calcula o tamanho da mensagem

section .text
    global _start

_start:
    ; Chamada de sistema sys_write (syscall número 1)
    mov rax, 1      ; Número da syscall: sys_write
    mov rdi, 1      ; File descriptor (1 = stdout)
    mov rsi, msg    ; Ponteiro para a string
    mov rdx, len    ; Comprimento da string
    syscall         ; Invoca o kernel

    ; Chamada de sistema sys_exit (syscall número 60)
    mov rax, 60     ; Número da syscall: sys_exit
    xor rdi, rdi    ; Código de saída 0
    syscall         ; Finaliza o programa


```

🟢 Exemplo - Hello World → exemplo de *linguagem de baixo nível* que tem por objetivo imprimir na tela a mensagem "Hello World!".

```c

/* Nome do Programa: Hello World!
   Programador: 
   Data: 16/03/2025
   Descrição: Este programa imprime a mensagem "Hello World!" */

/* Biblioteca de entrada/saída de dados */
#include <stdio.h>

/* Função principal */
int main (void) {
    
    printf("Hello World!\n"); // Imprime a mensagem "Hello World!"
   
    return 0; 
    
} /* Fim da função main */

```

🟢 Exemplo - Hello World!→ Um programa em C *de alto nível* que imprime a mesma mensagem, "Hello World!". 


> Enquanto o Assembly exige manipulação direta dos registradores e chamadas explícitas ao kernel, C permite um código mais limpo e 

> legível, sem perder o controle sobre o hardware.


🧪 Nos laboratórios da AT&T/Bell Labs em Murray Hill - Nova Jérsei, Denis Ritchie começou a trabalhar com o computador DEC PDP-11 em 

1972 e a partir de então, C começou a "tomar forma" como uma linguagem acessível e de *alto nivel* e, finalmente, em 

em 1973, com a inclusão de `structs` (estruturas) ela se tornou poderosa o suficiente para que o sistema operacional UNIX fosse todo 

reescrito em linguagem C.


O UNIX se tornou um sistema popular entre computadores e mainframes, e por ser um 

*software aberto*, a linguagem C rapidamente se espalhou entre os denvolvedores e 

muitos sistemas operacionais baseados em UNIX como macOS e GNU - Linux, além do 

Microsoft Windows passaram a ser escritos em C e muitas outras linguagens de 

programação criadas a partir de então se basearam em C como *Java* e *C++*.  


## **📌 *Por quê aprender C?**


Eis a pergunta que não quer calar: por quê? 🤷🏻‍♂️


Apesar de ter sido criada nos anos 70, C é uma linguagem moderna e ainda é amplamente utilizada e valorizada no mercado. Aprender C

não é apenas aprender mais uma linguagem, mas sim entender como os computadores realmente funcionam.

✅ Motivos para aprender C

1️⃣ Fundamento para outras linguagens

* Muitas linguagens modernas como C++, Java, Python e Go foram influenciadas por C.

* Se você entende C, aprender essas linguagens se torna muito mais fácil.

2️⃣ Desempenho e Eficiência

* C permite manipulação direta de memória, endereços e hardware, garantindo programas altamente eficientes.

* É amplamente utilizado em desenvolvimento de sistemas embarcados, drivers e software de alto desempenho.

3️⃣ Controle Total sobre o Hardware

* Ao contrário de linguagens de alto nível, C não esconde como o hardware realmente funciona.

* Ideal para quem deseja trabalhar com sistemas operacionais, firmware e programação embarcada.

4️⃣ Base da Computação

* Sem C, a computação moderna não existiria da mesma forma. Ele está presente no 

desenvolvimento de compiladores, interpretadores, bancos de dados e sistemas 

operacionais.

* É a linguagem do UNIX, do Linux, e de grandes partes do Windows e macOS.


> Dominar C é mais do que aprender uma linguagem: é aprender a falar diretamente com o computador. Se você quer entender computação 
> de verdade, C é o caminho. 🚀


## 📌 **Compilador GCC - Instalando no seu Sistema**

Agora vamos sugerir e orientar como instalar os compiladores e gerenciadores no computador para que possa começar a programar em C.

Utilizaremos o compilador `gcc` para Windows e distribuições Linux (Ubuntu, Debian, Fedora, dentre outros) e `xcode` no macOS para os 

dispositivos da Apple. 


💻 Microsoft Windows 


* Primeiro, vamos baixar o compilador `gcc` através do programa MinGW que pode ser baixado nesse site:

https://sourceforge.net/projects/mingw/


* Após o download, instalaremos o programa MinGW executando ele e seguindo as instruções da tela (Install, Continue...).


* Com MinGW instalado, no canto esquerdo do programa *selecione* a opção *Basic Setup*, e depois *mingw32-base* e *mingw32-gcc-g++*, 


> Observe que o MinGW oferece o download e a instalação de compiladores de outras linguagens de programação como Ada, Basic e FORTRAN 

> caso o usuário se envolva nessas linguagens também! 🤓💾


* Após selecionar o *mingw32-gcc-g++*, volte no canto superior esquerdo e selecione *Installation* e depois *Apply Changes*, com isso 

o compilador gcc será instalado no computador.

* Finalmente, após a instalação, virá uma mensagem com três opções de botão a escolher e selecione *Apply*.


⚠️ Não é obrigatório mas é altamente recomendado configurar o PATH no Windows para que o programa, independente da IDE de 

desenvolvimento ou terminal de comando a ser executado, C possa ser compilado com sucesso!

Para configurar o PATH:

* Vá a *aba ou botão de pesquisa* que fica ao lado do botão *Iniciar* e digite *Editar as variáveis de ambiente do sistema* e selecione.

* Depois vá na parte superior da janela e procure a aba *Avançado* e depois selecione o botão *Variáveis de Ambiente*.

* Vai aparecer uma janela com uma coluna "variável" e selecione a opção *Path* e clica no botão *Editar...*.

* Na outra janela, clique em qualquer linha em branco e selecione o botão à direita *Editar*, digite `C:\MinGW\bin` e clica no botão 

*Ok*.

Confirmando todas as aplicações de janelas posteriores, instalamos e configuramos o ´gcc´ no PATH do Windows.


✅ Testando se o gcc está instalado.

Copie o código abaixo e salve no programa *Bloco de Notas* como *teste.c* . 

```c


/* Nome do Programa: Hello World!
   Programador: 
   Data: 16/03/2025
   Descrição: Este programa imprime a mensagem "Hello World!" */

/* Biblioteca de entrada/saída de dados */
#include <stdio.h>

/* Função principal */
int main (void) {
    
    printf("Hello World!\n"); // Imprime a mensagem "Hello World!"
   
    return 0; 
    
} /* Fim da função main */


```

Depois, entre no CMD do Windows ou no Power Shell. Acesse o local onde foi salvo o seu arquivo *teste.c*. Para saber quais pastas 

estão disponíveis no local em que está direcionado no *cmd/Power Shell* digite o comando `dir` para listar as pastas. Se após digitar 

*dir* e a pasta *Documentos* estiver listada, acesse o seu arquivo digitando: 

```

cd Documentos 


```

Se não tiver listado a pasta o qual salvou o seu arquivo *teste.c*, digite o comando *cd PASTA* seguidamente até achar o local que 

está salvo o arquivo.

Após acessar a pasta onde está teste.c, digite o comando:

```

gcc teste.c -o teste.exe


```

Se não aparecer nenhuma mensagem, significa que o `gcc` foi instalado com sucesso e que seu arquivo foi *compilado* com sucesso.

Agora, digite 

```

.\”teste.exe”


```

que vai aparecer a mensagem

```

Hello World! 


```

e seu programa em C foi executado com sucesso!

 📌 Fontes: [Compilando e executando programas em C/C++ no Windows](https://www.alura.com.br/artigos/compilando-executando-programas-c-c-windows)  


🐧 Linux 


> Para instalar o compilador `gcc` em uma distribuição Linux, recomendo fortemente que pesquise o compilador `gcc` na loja de 

> aplicativos da distribuição utilizada! Vale lembrar que, mesmo que não tenha sido instalado repositórios proprietários no 

> sistema, como o `gcc` é livre, ele está disponível em repositórios nativos da distribuição seja Debian, Ubuntu, Fedora, dentre 

> outros. 


Caso queira instalar por meio do *terminal de comando* use o seguinte comando:


🟢 Linux (Debian/Ubuntu e derivados)

* Para distribuições com pacotes `.deb` utilize o seguinte comando no terminal: 

```bash

sudo apt update && sudo apt install build-essential

```

No Debian, o `gcc` pode também ser encontrado e instalado no *Gerenciador de Pacotes Synaptic* com muita facilidade e 

fluidez.


⚠️ O Gerenciador de Pacotes Synaptic do Debian gerencia todos os pacotes disponíveis utilizados pelo sistema Debian. Cuiado ao 

manipulá-los pois isso pode comprometer a usabilidade do sistema operacional!


🟢 Fedora (Red Hat, Suse e derivados)

* Para distribuições com pacotes `.rpm` utilize o seguinte comando no terminal:


```bash

sudo dnf install gcc


```

*Para conferir se instalou tudo certinho, digite:


```bash

gcc --version

```


🟢 Linux (Arch e derivados)

* No terminal digite o seguinte comando:

```bash

sudo pacman -S base-devel

```


🍏 macOS

* Para instação do `xcode` da Apple, digite o seguinte comando no terminal:

```bash

xcode-select --install

```

* Para confirmar a instalação digite:

```bash

gcc --version

```

📌 Caso queira instalar o pacote `gcc` oficial:

* Instalar o `gcc` via Homebrew


1️⃣ Instale o Homebrew (se ainda não tiver):

```bash

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


```


```bash

brew install gcc


```

* Pra ver se instalou tudo corretamente, digite:

```bash

gcc --version

```

## 📌 **Conclusão**

A linguagem C não é apenas mais uma linguagem de programação; ela é a base sobre 

a qual a computação moderna foi construída. Sistemas 

operacionais, compiladores, bancos de dados, dispositivos embarcados e até 

linguagens mais recentes se originam ou dependem de C.

Aprender C não é só aprender a programar, é aprender como os computadores 

realmente funcionam. É ganhar controle sobre o hardware, 

entender gerenciamento de memória, otimizar código para alta performance e 

desenvolver soluções que são executadas diretamente no 

coração dos sistemas computacionais.

Agora que você entende a história, domina os fundamentos e configurou seu 

ambiente, chegou a hora de transformar teoria em prática. Dominar C é mais do que 

aprender a programar—é entender a essência da computação. 

Nos próximos capítulos, vamos explorar mais a fundo a estrutura da linguagem e 

sua aplicação prática.

🚀 Prepare-se, porque sua jornada no mundo da programação C está apenas 

começando! 💾🔥


