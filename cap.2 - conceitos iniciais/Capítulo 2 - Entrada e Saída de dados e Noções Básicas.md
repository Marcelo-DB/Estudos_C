# Noções Básicas em C - Entrada e Saída de Dados

## **📌 Código em C - Hello World!**

Vamos começar nosso estudo em C com um simples código que todo programador faz ao iniciar uma nova linguagem de programação: **Hello World!**  

Isso mesmo, um código de "batismo" que todo programador constrói quando conhece ou começa a programar em uma nova linguagem. (Os supersticiosos dizem que isso dá sorte! 😎💻)  

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

🟢 1001 - Hello World!→ Extremamente Básico](https://www.beecrowd.com.br/judge/pt/problems/view/1001).

Vamos observar cada componente desse programa em C e comentá-lo a fim de explicar como funciona o código!

```c
/* Nome do Programa: Hello World!
   Programador: 
   Data: 16/03/2025
   Descrição: Este programa imprime a mensagem "Hello World!" */
```

Essa parte do programa em que as mensagens ficam entre /*......*/ nós chamamos de **comentário**. 

Eles servem para documentar o código, explicando a sua funcionalidade e tornando a leitura mais fácil.

O compilador ignora essas linhas, ou seja, *não afetam a execução do programa*.


> **Boa prática de programação!**
> Sempre coloque comentários explicativos em seu código! Isso torna o programa mais compreensível para você no futuro e para qualquer outra pessoa que precise analisá-lo.

```c
#include <stdio.h>
```

Essa linha importa a *biblioteca padrão de entrada e saída* em C <stdio.h>.

>Sem essa biblioteca, não podemos usar funções como 
printf e scanf, essenciais para exibir ou receber dados do usuário.

No caso deste código, *usamos printf para imprimir Hello World! na tela.*

```
int main (void){
...
}
```

* A função main() é a função principal de um programa em C.

* Todo código C precisa de uma função main(), pois é o ponto de entrada do programa.

* Dentro dela, colocamos as instruções que serão executadas, como a exibição da mensagem "Hello World!".

```
c
printf("Hello World!\n");
```

* printf() é uma função da biblioteca stdio.h usada para exibir texto na tela.

* O texto a ser impresso deve estar sempre entre aspas duplas ("...").

* O \n no final da string é um caractere especial de nova linha, ou seja, faz com que o cursor pule para a próxima linha após imprimir a mensagem.

✅ Sintaxe padrão do printf():

```c
printf("FRASE A SER ESCRITA");
```

📌 A Instrução return 0;

```c
return 0;
```

* Esta linha indica que o programa foi finalizado corretamente.
  
* return 0; é uma boa prática em C, pois retorna o valor 0 ao sistema operacional, sinalizando que a execução foi bem-sucedida.
  
Vamos explorar mais sobre *return* no Capítulo 5 - Funções.

## 📥 Como Rodar o Código

Se você quiser rodar este código no seu computador, siga os passos abaixo:

🪟 Windows (CMD)

```bash
gcc helloworld.c -o helloworld
./helloworld.exe
```

🪟 Windows (PowerShell)

```powershell
gcc helloworld.c -o helloworld
./"helloworld.exe"
```

🐧 🍏 Linux/macOS

```terminal
gcc helloworld.c -o helloworld
./helloworld
```

Agora é só executar e ver a mágica acontecer! 🎩✨


📌 Saída esperada do programa

Após compilar e rodar o código, a saída será:

```
c
Hello World!
```

🎉 Parabéns! Você acabou de rodar seu primeiro programa em C!


## **📌 Área do Círculo e Produto Simples**

Como disse o astronauta Neil Armstrong ao pisar na Lua:

"Este é um pequeno passo para um homem, mas um salto gigantesco para a humanidade." 🚀🌕

Assim como esse marco na história, dar os primeiros passos na programação em C pode parecer simples, mas representa um avanço enorme na nossa jornada como desenvolvedores.

Neste capítulo, vamos explorar duas construções essenciais para o desenvolvimento de qualquer programa em C:

✅ Declaração de variáveis
✅ Entrada de dados

E para isso, resolveremos dois problemas clássicos do Beecrowd:

🟢 1002 - Área do Círculo → Aprenderemos a usar números de ponto flutuante (double) e a função scanf() para receber valores do usuário.

🟢 1004 - Produto Simples → Trabalharemos com operações matemáticas básicas e formataremos a saída corretamente.
Agora, bora codar! 💻🔥

### **📌 Produto Simples

```c
/* Nome do Programa: prod_simples.c
   Programador: 
   Data: 16/03/2025
   Descrição: Este programa lê dois valores inteiros
   e imprime o produto desses dois inteiros*/

/* Biblioteca de entrada/saída de dados */
#include <stdio.h>

/* Função principal */
int main (void) {
    
    /*Declaração de variáveis*/
    int a;
    int b;
    int produto;
    
    /*Leia dois inteiros*/
    scanf("%d %d", &a, &b);
    
    /*Atribui o produto entre os inteiros a e b na variável produto*/
    
    produto = a * b;
    
    /*Imprime o resultado*/
    printf("PROD = %d\n", produto); // Imprime o resultado do produto
   
    return 0; 
    
} /* Fim da função main */
```

🟢 1004 - Produto Simples → Trabalharemos com operações matemáticas básicas e formataremos a saída corretamente.


Só pra deixar mais claro, o exercício do círculo, faremos o código posteriormente porque vamos falar sobre tipos de variáveis em C.

```c

    /*Declaração de variáveis*/
    int a;
    int b;
    int produto;
```

Observe que na declaração de variáveis há duas situações acontecendo:

* Temos o *tipo* da variável que no caso é um número inteiro e foi declarado como int.

* Temos também o *nome* da variável que foi atribuído na memória, no caso, há três nomes:
a, b e produto. 

* Esses *nomes* são atribuídos de forma livre pelo programador, entretanto,
há algumas regras a serem seguidas em C para os nomes das variáveis:

|                           Regra              		       |                     Exemplo válido                |
|--------------------------------------------------------------|---------------------------------------------------|
|   Pode conter letras, números e começar com underscore (_)   |           idade,total_vendas,contador       |          
|       Deve começar com uma letra ou underscore (_)           |                  nome, _variavelAux           |
|      Não pode ser uma palavra reservada da linguagem         |             int e return são proibidos        |
|      Diferencia maiúsculas de minúsculas (case-sensitive)    |                Variável ≠ variavel            |
|Não pode conter espaços ou caracteres especiais ($,*,$, etc.) | totalVendas (válido) / total vendas (inválido)|
|  Deve ser descritiva para melhorar a legibilidade do código. |            media_alunos ao invés de m         |
 
* Tabela 2.1 - Regras de declaração de variáveis.

```c
/*Leia dois inteiros*/
    scanf("%d %d", &a, &b);
```

Nesta parte do código fonte em C, temos a entrada de dados.

* A função scanf lê dois números inteiros indicados por %d e atribui essa entrada em &a e &b.

* O símbolo & (operador de endereço) indica que o valor lido pelo usuário deve ser armazenado no endereço de memória da variável correspondente (a e b), garantindo que a entrada seja salva corretamente.

> Em breve faremos uma explicação mais detalhada em como funciona a memória e o alocamento de diversos
tipos de variáveis em C (char, int, double, long double, etc.).

```c
/*Atribui o produto entre os inteiros a e b na variável produto*/
    
    produto = a * b;
```

Aqui chegamos ao objetivo principal do programa: a multiplicação de dois números inteiros!

* Observe que a e b são multiplicados * e o resultado atribuído a variável produto na memória do computador.

* Principais operadores em C: adição (+), subtração (-), multiplicação (*), divisão (/) e resto (%). Outros operadores e atribuições serão explicados no decorrer dos estudos conforme códigos e algoritmos do Beecrowd forem explicados.

> O % (módulo) retorna o resto da divisão inteira entre dois números. 
	Exemplo: 10 % 3 resulta em 1.


```c
    /*Imprime o resultado*/
    printf("PROD = %d\n", produto); // // Imprime o resultado do produto
```

Finalmente, imprimimos o resultado da multiplicação com a função *printf* que já comentamos na seção anterior com o programa Hello World mas com alguns diferenciais:

* Primeiramente, observe que na sintaxe do printf "PROD = %d\n" essa informações estão *entre aspas* assim como a palavra Hello World! estava entre aspas e, assim como no programa anterior, essa frase será impressa ao executar o programa.

* A diferença é que, além da palavra PROD =  será impresso %d que é um número do tipo *inteiro* associado a variável produto
declarada após a vírgula (..., produto);).

### 📥 Como Rodar o Código

Salvando o código, por exemplo, como multiplica.c no seu computador, siga os passos abaixo:

🪟 Windows (CMD)

```bash
gcc multiplica.c -o multiplica
./multiplica.exe
```

🪟 Windows (PowerShell)

```powershell
gcc multiplica.c -o multiplica
./"multiplica.exe"
```

🐧 🍏 Linux/macOS

```terminal
gcc multiplica.c -o multiplica
./multiplica
```

Agora é só executar e conferir de a multiplicação dá certo! 🎩✨

Vamos agora partir para o próximo e último exemplo desse capítulo.


### **📌 Área do Círculo**

```c
/* Nome do Programa: area_circulo.c
   Programador: 
   Data: 16/03/2025
   Descrição: Este programa calcula o valor da área de um círculo,
   lê um número real e calcula a sua área.*/

/* Biblioteca de entrada/saída de dados */
#include <stdio.h>
#define PI 3.14159 //insere um valor fixo para o valor do número PI

/* Função principal */
int main (void) {
    
    /*Declaração de variáveis*/
    double numero, area;
    
    /*Leia um número real*/
    scanf("%lf", &numero);
    
    /*Realiza o cálculo da área de uma circunferência*/
    
    area = numero * numero * PI;
    
    /*Imprime o resultado*/
    printf("A=%.4f\n", area); // Imprime o resultado da área da circunferência
   
    return 0; 
    
} /* Fim da função main */
```

🟢 1002 - Área do Círculo → Aprenderemos a usar números de ponto flutuante (double) e a função scanf() para receber valores do usuário.

📌 Análise do Código

Este problema do Beecrowd (1002 - Área do Círculo) ensina a trabalhar com números de ponto flutuante (double) e a função scanf() para 

receber valores do usuário.

1️⃣ Entendendo o Pré-Processador (#define)

No início do código, temos a seguinte linha:

```c

/* Biblioteca de entrada/saída de dados */
#include <stdio.h>
#define PI 3.14159 //insere um valor fixo para o valor do número PI
```

Essa diretiva do pré-processador tem algumas funções importantes:

✔ Criação de uma constante simbólica:

Define PI como 3.14159, permitindo que seja usada no código sem precisar digitá-la manualmente.

✔ Facilidade de manutenção:

Se o valor de PI precisar ser alterado, basta modificar apenas essa linha, sem precisar procurar e substituir em todo o código.

❗ Atenção: Nunca coloque ; ao final de um #define, pois as diretivas do pré-processador não são comandos da linguagem C, e um 

ponto e vírgula causaria erro na compilação.


2️⃣ Declaração de Variáveis


No bloco abaixo, dentro da função main(), temos a declaração de duas variáveis:

```c

/*Declaração de variáveis*/
    double numero, area;
```

✔ double → Tipo de dado utilizado para armazenar *números reais (ponto flutuante)* com maior precisão.

✔ numero → Armazena o valor digitado pelo usuário.

✔ area → Armazena o resultado do cálculo da área da circunferência.


3️⃣ Tipos de Números Reais em C

A linguagem C oferece três tipos principais para representar *números reais (ponto flutuante)*:


🟢 float (Precisão Simples)

Representa números reais de precisão simples (geralmente 32 bits).

Possui cerca de 6 a 7 dígitos significativos de precisão.

Usa menos memória, mas pode perder precisão em cálculos mais complexos.

📌 Exemplo:

```c

/*Declaração da variável pi em float com 4 casas decimais*/
    float valor = 3.1415;
```

🔵 double (Precisão Dupla)

Representa números reais de precisão dupla (geralmente 64 bits).

Possui cerca de 15 a 16 dígitos significativos, ou seja, mais precisão do que float.

Muito usado para cálculos científicos e financeiros.

📌 Exemplo:

```c

/*Declaração do número pi em double com mais precisão numérica*/
    double pi = 3.14159265358979;
```

🟠 long double (Precisão Estendida)

Representa números reais de precisão estendida (geralmente 80 ou 128 bits, dependendo do compilador e da arquitetura).

Possui ainda mais casas decimais do que double.

Pouco utilizado na prática, pois double já é suficiente para a maioria dos casos.

📌 Exemplo:

```c

/*Declaração do número pi em long double com maior precisão numérica em C*/
long double constante = 3.141592653589793238;
```

Quando usar cada um?

✅ float → Quando precisar de menos consumo de memória e precisão baixa for aceitável.

✅ double → Quando precisar de boa precisão para cálculos matemáticos (é o mais usado).

✅ long double → Quando for necessário trabalhar com números extremamente precisos, como em simulações científicas.


4️⃣ Por que não usar apenas long double em todo o código?

Se long double tem mais precisão, por que não padronizar tudo nele? A resposta está na eficiência do programa e no uso de memória (lembre-se que a memória é um espaço com números binários 0s e 1s:

✔ Eficiência computacional:

Quanto mais bits um número ocupa, mais memória ele consome e mais lento pode ser o processamento.

✔ Necessidade do projeto:

float pode ser suficiente para cálculos menos exigentes.

double é um equilíbrio entre precisão e desempenho.

long double só é necessário quando se precisa de extrema precisão (exemplo: cálculos astronômicos).


5️⃣ Leitura dos Dados (scanf)

```c

/*Leia um número real*/
    scanf("%lf", &numero);
```

Aqui, a função scanf() lê um número digitado pelo usuário e armazena na variável numero.

⚠ Atenção ao formato:

%lf → Indica que o valor lido será armazenado em uma variável do tipo double.

Se fosse um float, usaríamos %f.


6️⃣ Cálculo da Área

```c

/*Realiza o cálculo da área de uma circunferência*/
    
    area = numero * numero * PI;
```

✔ Multiplica o raio ao quadrado (numero * numero) pelo valor de PI, seguindo a fórmula matemática da **área do círculo** (A = π r^2).


7️⃣ Impressão do Resultado

```c

    /*Imprime o resultado*/
    printf("A=%.4f\n", area); // Imprime o resultado da área da circunferência
```

Finalmente, a impressão do resultado com a variável ´area´ na saída ´printf´.

Aqui, a função ´printf()´ exibe o resultado:

+ ✔ %.4f → Define a **precisão de 4 casas decimais** para a saída.

+ ✔ Se quisermos **duas casas decimais**, basta usar %.2f.

+ ✔ O especificador %f é usado para **formatar valores de ponto flutuante** (float, double e long double).

* Ao contrário das variáveis do tipo ´int´, no ´double´ ou em qualquer uma das declarações feitas anteriormente, a saída é sempre do 

tipo %f.


### 📥 Como Rodar o Código

Salvando o código, por exemplo, como area_circulo.c no seu computador, siga os passos abaixo:


🪟 Windows (CMD)

```bash
gcc area_circulo.c -o area_circulo
./area_circulo.exe
```

🪟 Windows (PowerShell)

```powershell
gcc area_circulo.c -o area_circulo
./"area_circulo.exe"
```

🐧 🍏 Linux/macOS

```bash
gcc area_circulo.c -o area_circulo
./area_circulo
```

Agora é só executar e verificar se a área do círculo está correta. 🎩✨

## 🚀 Conclusão

Agora você já entende como funciona um programa básico em C!

Vimos como usar comentários, bibliotecas, printf() e scanf() e return 0;.

No próximo capítulo, vamos explorar a parte de *programação estruturada* com repetição `if` e `else`.
