<h1>Entrada e Saída de dados</h1>



Todo o programa de computador é composto por 3 elementos básicos:

**Entrada:** Responsável por obter informações do usuário por meio do teclado, ou seja, é um Comando de Entrada de Dados. **Exemplo:** Digite 2 números: _.

**Processamento:** São as instruções do algoritmo responsáveis por processar as informações. **Exemplo:** Calcule a média dos 2 números digitados pelo usuário. 

**Saída:** Responsável por  mostrar os resultados do processamento na Tela do Computador, ou seja, é um Comando de Saída de Dados. **Exemplo:** Exibir na tela (console) o resultado do cálculo da média.

<div align="center"><img src="https://i.imgur.com/YNUpmlg.png" title="source: imgur.com" width="60%"/></div>

Neste material veremos as 2 pontas do processo, ou seja a **Entrada** e a **Saída**. O **Processamento** nós veremos no decorrer do curso, pois existem diversas opções.

Em Java Console, existem alguns Métodos (funções), que são responsáveis pela Entrada e Saída de dados, respectivamente:

-  **Saída:** 

  - #### Método printf();

  - #### Método print() e println().

- **Entrada:**

  - **Classe Scanner.**

<h2>1. Saída de dados</h2>

Os Métodos **printf(), print() e println()**, que pertencem a **Classe System**, são utilizados para mostrar informações no console (na tela do computador), ou seja, são Métodos de Saída de Dados em tela. 

Os Métodos de saída **printf(), print() e println()** utilizam o o dispositivo padrão de saída (**System.out**). **out** é uma variável da **Classe System**, que armazena a saída padrão do sistema, que geralmente é o **Console**.

<h3>1.2. Métodos de Saída</h3>

Na tabela abaixo, vemos as diferenças entre os 3 Métodos:

| Método        | Descrição                                                    |
| ------------- | ------------------------------------------------------------ |
| **print()**   | Permite exibir na tela uma cadeia de caracteres (String), sem se preocupar com a formatação, ou seja, do jeito que a String for enviada, ela será exibida. |
| **printf()**  | Permite exibir os dados na tela formatados (data, hora, moeda, entre outros) |
| **println()** | Equivalente ao Método print(). A diferença é que sempre pulará uma linha após mostrar o valor na tela. |

Os Métodos de saída de dados são responsáveis pela exibição dos dados de uma variável, constante ou objeto na tela do computador.

<h3>1.3 Métodos de Saída print() e println()</h3>

**Sintaxe:**

```java
System.out.println("texto" + variavel);

System.out.print("texto");
```

Observe que é possível além de exibir um texto na tela, também é possível exibir o valor de uma variável ao lado do texto, unindo o texto e a variável através de um sinal de soma **+**. O texto deve sempre estar sempre entre aspas. 

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/8/docs/api/java/lang/System.html" target="_blank"><b>Documentação: Classe System</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/8/docs/api/java/io/PrintStream.html" target="_blank"><b>Documentação: Classe System.out</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 01 - Hello World!**

```java
package helloworld;

public class Hello {

	public static void main(String[] args) {
		System.out.print("Olá Mundo!");

	}

}
```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

<div align="center"><img src="https://i.imgur.com/0LA7zSa.png" title="source: imgur.com" /></div>

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/01_helloworld" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 02 - Exibe os dados das Variáveis na tela - Versão 01**

```java
package exibir_variaveis;

public class ExibirVariaveis {

	public static void main(String[] args) {
		
		byte bit = 127;
		short valor = 254;
		int quantidade = 1000;
		long identificador = 10000l;
		float altura = 25.4f; 
		double area = 45.4567;
		char tipo = 'A';
		boolean resposta = true;
		String palavra = "Generation";
		
		System.out.println(bit);
		System.out.println(valor);
		System.out.println(quantidade);
		System.out.println(identificador);
		System.out.println(altura);
		System.out.println(area);
		System.out.println(tipo);
		System.out.println(resposta);
		System.out.println(palavra);

	}

}
```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

<div align="center"><img src="https://i.imgur.com/aNmi3qp.png" title="source: imgur.com" /></div>

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/02_exibir_variaveis" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

<h3>1.4 Método printf()</h3>

**Sintaxe:**

```java
System.out.printf(expressão_de_controle, argumento1, argumento2, ...);
```

Observe que o Método **printf()** sempre irá exibir uma Expressão de controle e o valor de uma ou mais variáveis (argumentos) depois da expressão. 

<h4>1.4.3 Expressão de Controle</h4>

A **Expressão de Controle** é uma sequência de caracteres  (portanto, delimitada por aspas duplas) que determina as informações que serão mostradas na tela. Nesta expressão podem existir dois tipos de  informações: 

- Caracteres comuns, ou seja, um texto qualquer;

- Códigos de controle (ou especificadores de formato). 

Os **códigos de controle**, mostrados na tabela abaixo, são utilizados para indicar o tipo de dado que será impresso na tela. Eles são  precedidos por um sinal de **porcentagem (%)** e são aplicados aos argumentos na mesma ordem em que eles irão aparecer na tela. É importante destacar que deve existir para cada código de  controle um argumento (Variável) correspondente. 

| Código | Formato (tipo de dados)                                      |
| ------ | ------------------------------------------------------------ |
| %c     | Caractere simples (char)                                     |
| %s     | Cadeia de caracteres (String)                                |
| %d     | Inteiro (int ou long)                                        |
| %f     | Real com ponto flutuante (float ou double)                   |
| %.2f   | Real com ponto flutuante (float ou double), delimitando o número de dígitos que serão exibidos nas casas decimais. <br />No exemplo ao lado, serão exibidos 2 dígitos depois do ponto (separador de casas decimais). |
| %e     | Número real em notação científica com o “e” minúsculo (float ou double) |
| %E     | Número real em notação científica com o “E” maiúsculo (float ou double) |
| %%     | Imprimir o próprio caractere %                               |

Veja o exemplo abaixo:

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 03 - Exibe na tela os dados das Variáveis formatados**

```java
package exibir_variaveis;

public class ExibirVariaveis {

	public static void main(String[] args) {
		
		int quantidade = 1000;
		long identificador = 10000l;
		float altura = 25.4f; 
		double area = 45.4567;
		double tamanho = 650000000.00;
		char tipo = 'A';
		String palavra = "Generation";
		 
		System.out.printf("Variável quantidade = %d", quantidade);
		System.out.printf("Variável identificador = %d", identificador);
		System.out.printf("Variável altura = %.2f", altura);
		System.out.printf("Variável area = %.2f", area);
		System.out.printf("Variável tamanho = %e", tamanho);
		System.out.printf("Variável tamanho = %E", tamanho);
		System.out.printf("Variável tipo = %c", tipo);
		System.out.printf("Variável palavra = %s", palavra);

	}

}
```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```bash
Variável quantidade = 1000Variável identificador = 10000Variável altura = 25,40Variável area = 45,46Variável tamanho = 6,500000e+08Variável tamanho = 6,500000E+08Variável tipo = AVariável palavra = Generation
```

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/03_exibir_variaveis_formatadas" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

Observe na imagem acima, que diferente do **Método println()**, todas as variáveis foram exibidas em uma única linha, se tornando difícil a leitura.

Vamos resolver este problema utilizando um recurso chamado **Caracteres de Escape**, que são instruções inseridas geralmente no começo ou no final de um texto, para sinalizar uma interpretação alternativa de uma série de caracteres. No Java, **um caractere precedido por uma barra invertida \ é uma sequência de escape**. Veja a tabela abaixo:

| Caractere de escape | Descrição                                                    |
| ------------------- | ------------------------------------------------------------ |
| \n                  | Nova linha                                                   |
| \t                  | Tabulação horizontal (o mesmo que pressionar a tecla Tab)    |
| \r                  | "Retorno do carro". É um escape de controle, que move o cursor do Terminal para o inicio da linha. |
| \b                  | Backspace. Faz o papel da tecla Backspace do seu teclado: move o cursor uma posição ou excluí um único caractere a esquerda da linha. |
| \\'                 | Aspas simples                                                |
| \”                  | Aspas dupla                                                  |
| \\\                 | Barra invertida                                              |

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 04 - Exibe na tela os dados das Variáveis formatados - Versão 02**

```java
package exibir_variaveis;

public class ExibirVariaveis {

	public static void main(String[] args) {
		
		int quantidade = 1000;
		long identificador = 10000l;
		float altura = 25.4f; 
		double area = 45.4567;
		double tamanho = 650000000.00;
		char tipo = 'A';
		String palavra = "Generation";
		 
		System.out.printf("\nVariável quantidade = %d", quantidade);
		System.out.printf("\nVariável identificador = %d", identificador);
		System.out.printf("\nVariável altura = %.2f", altura);
		System.out.printf("\nVariável area = %.2f", area);
		System.out.printf("\nVariável tamanho = %e", tamanho);
		System.out.printf("\nVariável tamanho = %E", tamanho);
		System.out.printf("\nVariável tipo = %c", tipo);
		System.out.printf("\nVariável palavra = %s", palavra);

	}

}
```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```bash
Variável quantidade = 1000
Variável identificador = 10000
Variável altura = 25,40
Variável area = 45,46
Variável tamanho = 6,500000e+08
Variável tamanho = 6,500000E+08
Variável tipo = A
Variável palavra = Generation
```

Observe na imagem acima, que **todas as variáveis foram exibidas uma em cada linha**, graças a **Sequência de Escape \n**. Agora que cada variável está sendo exibida em uma linha, podemos observar alguns detalhes na formatação:

- Nas variáveis altura e área, foi utilizado o formatador **%.2f**, que indica que um número de ponto flutuante (casas decimais) será exibido com apenas 2 dígitos de precisão nas casas decimais, fazendo arredondamentos onde for necessário;
- Observe que como estamos formatando a saída dos números float e double, o separador de casas decimais **ponto** (padrão Americano), foi substituído pela **virgula**, seguindo padrão do nosso Sistema Operacional Windows, que está em Português Brasil;
- Na variável tamanho, foram utilizados os formatadores **%e** e **%E**, que indica que um número de ponto flutuante (casas decimais) será mostrado utilizando a **notação científica** com o **e (minúsculo)** e com o **E (maiúsculo)**, respectivamente. **Exemplo:** 74000 é equivalente a 7,4 E+04, onde o **E** é a **base da potência (10)** e o **+04 é o expoente da potência**;

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/04_exibir_variaveis_formatadas_v2" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

<h2>2. Entrada de dados </h2>

A **Classe Scanner** é utilizada quando se deseja obter informações do usuário por meio do teclado, ou seja, é uma Classe que oferece alguns Métodos de Entrada de Dados. A Classe Scanner pertence ao Pacote **java.util** e para utilizarmos precisamos instanciar um Objeto desta Classe em nosso código, como mostra o trecho de código abaixo:

**Sintaxe:**

```java
Scanner leia = new Scanner(System.in);
```

O Objeto **leia**, da Classe Scanner, foi criado e instanciado para efetuar a leitura via teclado, usando o dispositivo padrão de entrada (System.in). **in** é uma variável da Classe System, que armazena a entrada padrão do sistema, que geralmente é o teclado, mas poderia ser um arquivo de texto também.

> Instanciar um Objeto **é um processo por meio do qual se realiza a cópia de um Objeto (definido por uma Classe) existente**. Uma classe, tem a função de definir um tipo de dado, que deve ser instanciado para que possamos utilizá-la. 
>
> Veremos estes conceitos com mais detalhes no tópico **Orientação a Objetos**.

Ao instanciar um Objeto da Classe Scanner, o Pacote **java.util.Scanner** será importado para a sua aplicação através da palavra reservada **import**, antes do nome da sua Classe. Veja o exemplo abaixo:

```java
import java.util.Scanner;

public class EntradaDeDados {

	public static void main(String[] args) {
        
        Scanner leia = new Scanner(System.in);
       
    }
    
}	
```

Observe que a instrução **import** foi adicionada antes do nome da Classe.

> A palavra reservada **import** da linguagem Java tem como objetivo disponibilizar em uma classe o acesso a  outras classes que estejam em pacotes diferentes. 
>
> Um **Pacote** ou **Package** na tecnologia Java nada mais é do que um conjunto de classes localizadas na mesma estrutura hierárquica de pastas. 
>
> Veremos estes conceitos com mais detalhes no tópico **Métodos**.   

<br />

<h3>2.1. Lendo instruções</h3>

Usa-se o Objeto da Classe Scanner (em nosso exemplo chamamos de **leia**), que foi instanciado no inicio do programa, quando é necessário que o usuário digite algum dado, que será armazenado em uma variável. 

A Classe Scanner possui uma série de Métodos de leitura de dados via teclado, que será utilizado de acordo com o tipo de variável. Veja a tabela abaixo:

<h3>2.1. Métodos de Entrada - Classe Scanner</h3>



| Método                    | Descrição                                                    | Tipo de dado |
| ------------------------- | ------------------------------------------------------------ | ------------ |
| **String next()**         | Faz a leitura, via teclado, de uma cadeia de caracteres simples, ou seja, que não usa o caractere espaço em branco. | String       |
| **next().charAt(0)**      | Faz a leitura, via teclado, de um único caractere simples, exceto o caractere espaço em branco. | char         |
| **String nextLine()**     | Faz a leitura, via teclado, de uma cadeia de caracteres, incluindo o caractere espaço em branco. | String       |
| **int nextInt()**         | Faz a leitura, via teclado, de um número inteiro de 32 bits. | int          |
| **long nextLong()**       | Faz a leitura, via teclado, de um número inteiro de 64 bits. | long         |
| **float nextFloat()**     | Faz a leitura, via teclado, de um número em notação de ponto flutuante normalizada em precisão dupla de 32 bits (usado para receber valores reais) | float        |
| **double nextDouble()**   | Faz a leitura, via teclado, de um número em notação de ponto flutuante normalizada em precisão dupla de 64 bits (usado para receber valores reais ou científicos) | double       |
| **boolean nextBoolean()** | Faz a leitura, via teclado, de um valor boolean (true ou false). | boolean      |

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/8/docs/api/java/io/InputStream.html" target="_blank"><b>Documentação: Classe System.in</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html" target="_blank"><b>Documentação: Classe Scanner</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 05 - Entrada de dados - simples**

```java
package classe_scanner;

import java.util.Scanner;

public class EntradaDeDados {

	public static void main(String[] args) {
		
		Scanner leia = new Scanner(System.in);
		
		int quantidade;
		long identificador;
		float altura; 
		double area;
		char tipo;
		String frase;
		boolean ativo;
		
		System.out.println("\nDigite um valor para a Variável quantidade (int): ");
		quantidade = leia.nextInt();
		
		System.out.println("\nDigite um valor para a Variável identificador (long): ");
		identificador = leia.nextLong();
		
		System.out.println("\nDigite um valor para a Variável altura (float): ");
		altura = leia.nextFloat();
		
		System.out.println("\nDigite um valor para a Variável area (double): ");
		area = leia.nextDouble();

		System.out.println("\nDigite um valor para a Variável tipo (char): ");
		tipo = leia.next().charAt(0);
				
		System.out.println("\nDigite um valor para a Variável frase (String): ");
		leia.skip("\\R?");
		frase = leia.nextLine();
		
		System.out.println("\nDigite um valor para a Variável ativo (boolean): ");
		ativo = leia.nextBoolean();
		
		System.out.println("\nDados recebidos via teclado:\n");
		
		System.out.println("\nVariável quantidade = " + quantidade);
		System.out.println("\nVariável identificador = " + identificador);
		System.out.println("\nVariável altura = " + altura);
		System.out.println("\nVariável area = " + area);
		System.out.println("\nVariável tipo = " + tipo);
		System.out.println("\nVariável palavra = " + frase);
		System.out.println("\nVariável tamanho = " + ativo);

	}

}

```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```bash
Digite um valor para a Variável quantidade (int): 
10

Digite um valor para a Variável identificador (long): 
1000

Digite um valor para a Variável altura (float): 
10,5

Digite um valor para a Variável area (double): 
10000,5454545455454

Digite um valor para a Variável tipo (char): 
a

Digite um valor para a Variável frase (String): 
Generation Brasil

Digite um valor para a Variável ativo (boolean): 
true

Dados Recebidos via teclado:

Variável quantidade = 10

Variável identificador = 1000

Variável altura = 10.5

Variável area = 10000.545454545545

Variável tipo = a

Variável palavra = Generation Brasil

Variável ativo = true
```

Observe no código acima que:

- Na entrada de dados das variáveis **float e double** (números reais), ao digitar os valores, observe que os números decimais foram separados por **virgula e não por ponto**, mas na hora e exibir as informações sem utilizar formatações, os números decimais foram separados por **ponto e não por vírgula**. A explicação é simples: Como o teclado está configurado para o formato **Português Brasil ABNT 2** e o Windows está configurado com o idioma **Português do Brasil**, ele utiliza a **virgula como separador de decimal**, seguindo o padrão do Brasil. Entretanto ao exibir os dados na tela, o Java segue o padrão Americano, que utiliza o ponto como separador de decimal, **exceto quando você utiliza o printf com formatação ou alguma Classe de formatação de números decimais do Java**. Inclusive se você digitar um número utilizando o ponto como separador de decimal será exibida a seguinte mensagem de erro no console: 

<div align="center"><img src="https://i.imgur.com/fLc8TgG.png" title="source: imgur.com" /></div>

*A mensagem acima indica que um tipo de dado diferente do esperado foi digitado.*

- A variável **char** (**tipo**) aceita **somente um único caractere**. Caso você digite mais de um caractere, não será exibida nenhuma mensagem erro no console, entretanto a variável guardará apenas o primeiro caractere digitado e irá ignorar os demais.
- Antes do comando de entrada de dados da variável String frase, observe que foi executado o Método **skip("\\R?")**. O Método **skip()** ignora a entrada que corresponde ao padrão especificado dentro dos parênteses, ignorando os  delimitadores. Em nosso exemplo, como foi executada a leitura de dados de variáveis de outros formatos (diferentes de String), antes de ler uma valor para a variável String, ao pressionar a tecla **enter** para finalizar a leitura, uma nova linha é gerada no console e o cursor foi movimentado para o inicio desta linha através do caractere de escape **\r** (retorno do carro). Com o Método **skip** estamos ignorando o caractere de escape **\r** e desta forma o comando **nextLine()** conseguirá efetuar a leitura via teclado de uma nova String. Se você não executar o Método **skip()** antes da leitura do valor via teclado, a Classe Scanner receberá o **\r** como o conteúdo da variável e como se trata de um caractere de escape, a variável frase ficará vazia (sem valor) e na sequência, fará a leitura do valor da próxima variável ( em nosso exemplo uma variável boolean).

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="100px"/> | <div align="left"> **ATENÇÃO:** Caso você esteja fazendo a leitura apenas de variáveis String, não será necessário utilizar o Método skip(). Utilize somente se você efetuar a leitura de variáveis de outros formatos antes da leitura da variável String.</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

- A variável **boolean (ativo)**, aceita **somente os valores true ou false**. Caso você digite outros valores, será exibida a seguinte mensagem de erro no console: 

<div align="center"><img src="https://i.imgur.com/vJyhLnv.png" title="source: imgur.com" /></div>

*A mensagem acima indica que um tipo de dado diferente do esperado foi digitado.*

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/05_entrada_de_dados" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

<h2>3. Comentários no código</h2>

A inserção de comentários no decorrer do algoritmo facilita a leitura deste por você e por outras pessoas desenvolvedoras. Os comentários são uma excelente alternativa para auxiliar nos estudos, porque ajudam a relembrar o como você implementou o seu código. Veja abaixo algumas formas e inserir comentários no seu código:

**Sintaxe:** 

```java
// Meu Comentário

/* Bloco de Comentários */

/** 
* Bloco de Comentários
*/
```

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>**Exemplo 06 - Hello World com comentários**

```java
/** 
 * Área reservada para importar os
 * Pacotes.
 * 
 * */
public class Hello {

	public static void main(String[] args) {
		
		// Exibe a Mensagem na tela
		System.out.print("Olá Mundo!");

	}

}

```

Observe que todas as linhas do código possuem comentários. A Execução do programa não muda em nada, porque o Java ignora tudo que estiver comentado.

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/entrada_saida/06_helloworld_comentarios" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

------

## 🔑**Pontos chave:**

1. **Entrada:** Responsável por obter informações do usuário por meio do teclado, ou seja, é um Comando de Entrada de Dados.
2. **Processamento:** São as instruções do algoritmo responsáveis por processar as informações.
3. **Saída:** Responsável por  mostrar os resultados do processamento na Tela do Computador, ou seja, é um Comando de Saída de Dados. 
4. Os Métodos **printf(), print() e println()**, que pertencem a **Classe System**, são utilizados para mostrar informações no console (na tela do computador), ou seja, são Métodos de Saída de Dados em tela. 
5. A **Classe Scanner** é utilizada quando se deseja obter informações do usuário por meio do teclado, ou seja, é uma Classe que oferece alguns Métodos de Entrada de Dados. 

<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="2%"/>Voltar</a></div>
