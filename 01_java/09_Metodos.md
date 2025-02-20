<h1>Métodos</h1>



Um **Método** é uma função associada à Classe, ou seja uma ação. Os Métodos permitem que a pessoa desenvolvedora modularize (divida) os programas, separando suas tarefas em unidades menores autocontidas. O Métodos são inspirados na conhecida Técnica do *“dividir para conquistar”*. Outra grande vantagem do uso de Métodos é que eles são reutilizáveis em futuros programas, evitando a repetição desnecessária de código.

**Exemplos de Métodos:**

- **Carro:** acelerar(), frear(), virar(), parar()
- **Conta Bancária:** sacar(), depositar(), transferir()
- **E-commerce:** pagar(), adicionarAoCarrinho()

Para promover a capacidade de reutilização de software, **todos os Métodos devem estar limitados à realização de uma única tarefa bem definida**. O **nome do método também deve ser assertivo e expressar essa tarefa efetivamente**. Os métodos tornam mais fácil as tarefas de escrever, depurar, manter e modificar programas, pelo simples fato de **um método que realiza apenas uma tarefa é mais fácil de testar e depurar do que um método maior que realiza muitas tarefas**.

Os métodos são essencialmente procedimentos que podem manipular atributos de objetos para os quais o método foi definido e receber **parâmetros por valor** através da **lista de argumentos** presentes na sua assinatura.

<br />

<h2>1. Declarando Métodos</h2>

**Sintaxe:**

<div align="center"><img src="https://i.imgur.com/rjKzQsM.png" title="source: imgur.com" /></div>

<br />

<h4>1.1. Modificador de Acesso</h4>

Determina como o Método será manipulado no decorrer do desenvolvimento do programa, ou seja, qual (is) Classes podem chamar (executar) o Método. Por hora vamos criar os nossos Métodos utilizando o Modificador de acesso **public** (acesso público, toda e qualquer Classe pode executar o Método), igual as nossas Classes. Este assunto será aprofundado em **Orientação a Objetos**.

<br />

<h4>1.2. Modificadores Non-Access</h4>

O modificador Non-Access  permite especificar algumas propriedades específicas, determinando como as Classes que herdarão o Método, podem ou não redefinir e/ou alterar o Método. Este assunto será aprofundado em **Orientação a Objetos**.

<br />

<h3>1.3. Tipo</h3>

É o indicador do valor de retorno do Método. Assim como as variáveis, geralmente os Métodos são definidos com os tipos de dados primitivos, como mostra a tabela abaixo:

| **Tipo**    | **Tamanho**                                               |
| ----------- | --------------------------------------------------------- |
| **boolean** | *true* ou *false*                                         |
| **char**    | 16  bits                                                  |
| **byte**    | 08  bits                                                  |
| **short**   | 16  bits                                                  |
| **int**     | 32  bits                                                  |
| **long**    | 64  bits                                                  |
| **float**   | 32  bits                                                  |
| **double**  | 64  bits                                                  |
| **String**  | **Não é um tipo primitivo, é um Objeto da Classe String** |

Caso você tenha dúvida sobre as regras de criação de variáveis, consulte o Conteúdo sobre <a href="03.md" >**Variáveis e Constantes**</a>. Os Métodos também podem retornar tipos de dados não primitivos, como Objetos de uma Classe, por exemplo. Em Orientação a Objetos, veremos este assunto com mais detalhes.

Os Métodos que possuem um tipo de dado, obrigatoriamente precisam retornar um valor equivalente ao seu tipo, ou seja, se o Método for do tipo **int**, ele precisa retornar um numero inteiro ao final do seu processamento. Para retornar este valor, o Java utiliza a palavra reservada **return**.

Caso o Método **não necessite ter um tipo de dado de retorno, ou seja, um valor que deverá ser retornado ao final da execução do Método**, Na assinatura do Método, defina o tipo do Método como **void**.

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html" target="_blank"><b>Documentação: Tipos de dados</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/7/docs/api/java/lang/String.html" target="_blank"><b>Documentação: Classe String</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://www.w3schools.com/java/ref_keyword_void.asp" target="_blank"><b>Documentação: Palavra reservada void</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://www.w3schools.com/java/ref_keyword_return.asp" target="_blank"><b>Documentação: Comando return</b></a></div>

<br />

<h3>1.4. Nome</h3>

É o nome do método.  Para definir o Nome dos Método, deve-se seguir algumas boas práticas:

- Por padrão o nome do Método, assim como nas variáveis, segue o padrão **Camel Case**, onde  sempre começa com letras minúsculas.  **Exemplos:** `copiar()`, `colar()`, `recortar()`
- Caso o nome do Método seja composto, a partir da segunda palavra utiliza-se a primeira letra maiúscula em cada palavra. **Exemplos:** `calcularSalario()`, `aplicarDesconto()`, `calcularAreaQuadrado()`
- O nome do Método deve possuir um verbo, porque indicam uma ação. **Exemplos:** `mover()`, `deletar()`, `inserirLinha()`
- O nome do Método deve ser assertivo e indicar exatamente o que ele faz. **Exemplos:** `copiarTexto()`, `colarTexto()`, `recortarTexto()`
- Independente de possuir ou não argumentos, um Método sempre terá os `( )` parênteses após o seu nome.
- Os identificadores não podem utilizar palavras reservadas, como: **`class`**, **`for`**, **`while`**, **`public`**, etc

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html" target="_blank"><b>Documentação: Palavras reservadas</b></a></div>

<br />

<h3>1.5. Argumentos</h3>

São os parâmetros do Método. São representados por uma **lista de variáveis separadas por vírgulas**, onde cada parâmetro obedece as regras e a sintaxe de definição de variáveis:

**Sintaxe:**

```java
[tipo] identificador
```

- **Tipo:** Tipo da variável.
- **Identificador:** Nome da variável.

Caso você tenha dúvida sobre as regras de criação de variáveis, consulte o Conteúdo sobre <a href="03.md" >**Variáveis e Constantes**</a>. As variáveis também podem ser de tipos de dados não primitivos, como Objetos de uma Classe, por exemplo. Em Orientação a Objetos, veremos este assunto com mais detalhes.

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html" target="_blank"><b>Documentação: Tipos de dados</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/> Exemplo 01: Método com retorno e argumentos

```java
	public static int soma(int s1, int s2) {
		return s1 + s2;
	}
```

No exemplo acima, o Método **soma** retorna um valor inteiro, ou seja, o comando **return** retornará um valor inteiro, no exemplo acima, a soma entre 2 números inteiros. Na definição do Método, utilizamos a palavra **static**, porque o Método será criado dentro da Classe main, onde todos os Métodos obrigatoriamente devem ser do tipo **static**.

> Um Método **static** é um Método da Classe, ou seja, são Métodos que não dependem de um Objeto, quando eles são invocados, executam uma função sem a dependência de um objeto ou instância de uma classe,  conseguindo chamar direto qualquer Método da classe. Veremos este assunto com mais detalhes em Orientação a Objetos.

Veja a implementação abaixo:

```java
package metodos;

public class Exemplo01 {

	public static void main(String[] args) {
        int resultado;
        
        resultado = soma(2, 2);
            
        System.out.println("O Resultado da soma é: " + resultado);
    }
    
    public static int soma(int numero1, int numero2) {
		return numero1 + numero2;
	}

}
```

<br />

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="100px"/> | <div align="left"> **ATENÇÃO:** O Método deve ser criado fora do escopo do Método main, mas dentro do escopo da Classe (em nosso exemplo, Exemplo01).</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br />

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Código:**

```bash
O Resultado da soma é: 4
```

Observe que para receber este valor, foi necessário criar uma variável do mesmo tipo de retorno do Método (no exemplo acima, uma variável do tipo **int**), associado a um comando de saída de dados, para exibir o conteúdo da variável.

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/blob/main/metodos/metodos/src/metodos/Exemplo01.java" target="_blank"><b>Código fonte</b></a>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/> Exemplo 02: Método sem retorno - void

```java
	public static void mensagem() {
		System.out.println("Método sem retorno (void)!");
	}
```

Métodos **void** não retornam valor, apenas exibem uma mensagem na tela ou realizam algum tipo de processamento sem retornar nenhum valor. No exemplo acima, o Método **mensagem** está exibindo uma mensagem na tela.

Para executar este Método, basta informar o nome dele:

```java
package metodos;

public class Exemplo02 {

	public static void main(String[] args) {
		mensagem();
	}

	public static void mensagem() {
		System.out.println("Método sem retorno (void)!");
	}
}
```

<br />

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Código:**

```bash
Método sem retorno (void)!
```

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/blob/main/metodos/metodos/src/metodos/Exemplo02.java" target="_blank"><b>Código fonte</b></a>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/> Exemplo 03: Calculadora com Métodos:

Vamos adaptar o exemplo da Calculadora, utilizando Métodos para realizar as Operações Matemáticas:

```java
package calculadora;

import java.util.Scanner;

public class Calculadora {

	public static void main(String[] args) {

		Scanner leia = new Scanner(System.in);

		float numero1 = 0, numero2 = 0;

		System.out.println("Digite o primeiro numero: ");
		numero1 = leia.nextFloat();

		System.out.println("Digite o segundo numero: ");
		numero2 = leia.nextFloat();

		// Exibe o Resultado de cada Operação Matemática:
		System.out.println("Soma = " + soma(numero1, numero2));
		System.out.println("Subtração = " + subtracao(numero1, numero2));
		System.out.println("Multiplicação = " + multiplicacao(numero1, numero2));
		System.out.println("Divisão = " + divisao(numero1, numero2));

		// Executa o Método void turma()
		turma();
        
        // Executa o Método float soma() com valores inseridos de forma direta
		System.out.println("\nSoma de valores inseridos de forma direta = " + soma(10.0f, 5.0f));
		
		//finaliza o Objeto leia
		leia.close();
		
	}

	// Método soma com 2 parâmetros float
	public static float soma(float numero1, float numero2) {
		return numero1 + numero2;
	}

	// Método subtracao com 2 parâmetros float
	public static float subtracao(float numero1, float numero2) {
		return numero1 - numero2;
	}

	// Método multiplicacao com 2 parâmetros float
	public static float multiplicacao(float numero1, float numero2) {
		return numero1 * numero2;
	}

	// Método divisao com 2 parâmetros float
	public static float divisao(float numero1, float numero2) {
		return numero1 / numero2;
	}

	// Método turma() do tipo void
	public static void turma() {
		System.out.println("\nCalculadora da Turma!!!!");
	}

}
```

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Código:**

```bash
Digite o primeiro numero: 
20
Digite o segundo numero: 
10
Soma = 30.0
Subtração = 10.0
Multiplicação = 200.0
Divisão = 2.0

Calculadora da Turma!!!!

Soma de valores inseridos de forma direta = 15.0
```

Observe que os Métodos **soma(), subtracao(), multiplicacao() e divisao()**, recebem 2 parâmetros (variáveis) do tipo  **float** e retornam o resultado da respectiva operação matemática através do comando **return**, que retornará um número também do tipo **float**. O Método **turma**, não retorna nenhum valor, por se tratar de um Método **void**. 

> **Porquê utilizamos 0.0f em variáveis float?**
>
> O **'f'** indica que você está inserindo um numero do tipo **float**. Se você escrever um número decimal sem o sufixo **'f'**, o Java entenderá que é um número de precisão dupla (double). 
>
> **Exemplos:**
>
> 0 é  int
> 0l é long
> 0.0 é double
> 0.0f é float 		

Execute o código e teste a calculadora.

| <img src="https://i.imgur.com/L338M2G.png" title="source: imgur.com" width="138px"/> | **DESAFIO:** *Quais melhorias poderiam ser realizadas no código da Calculadora? Análise o código acima e faça algumas melhorias no código e/ou implemente novas funções como Cálculo da Potência, Raiz Quadrada, entre outras. A melhor forma de aprender e compreender uma Linguagem de Programação é praticando! * |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/blob/main/metodos/metodos/src/metodos/Calculadora.java" target="_blank"><b>Código fonte</b></a>
<br />

<h2>2. Pacotes</h2>

No desenvolvimento de pequenas aplicações Java, pode ser viável manter todo o código em um mesmo diretório. Entretanto, para aplicações maiores, colocar todos os arquivos em um mesmo local, sem uma organização, pode aumentar significativamente a possibilidade de conflitos de classes (classes com o mesmo nome no mesmo escopo) e dificultar a localização de um determinado código, método ou criar problemas de visibilidade, que veremos mais adiante.

Em Java, a solução para esses problemas está na organização das classes em **pacotes**. Um **Pacote** ou **Package** na    tecnologia Java nada mais é do que um conjunto de classes localizadas na mesma estrutura hierárquica de pastas.    Usualmente, são colocadas em um **Pacote** todas as classes relacionadas, construídas com um propósito comum para    promover a reutilização de código. Na imagem abaixo, vemos o projeto Calculadora estruturado em Pacotes:

<div align="center"><img src="https://i.imgur.com/yXkxL7r.png" title="source: imgur.com" /></div>

*No pacote calculo, temos uma Classe, chamada Calculadora, onde foram implementados os Métodos da calculadora. No pacote aula_pacotes, temos a Classe TestaCalculadora, onde foram implementadas as entradas de dados e as chamadas para os Métodos.*

O próprio código base da tecnologia Java está todo estruturado em pacotes, como pode ser observado na especificação da API (*Application Programming Interface*, ou Interface de Programação de Aplicações) da plataforma Java SE, apresentada parcialmente na tabela abaixo:

| **Pacote API**  | **Suporta**                                                  |
| --------------- | ------------------------------------------------------------ |
| **java.awt**    | **Recursos gráficos**: botão, barra, caixas de texto, janela, entre outros |
| **java.io**     | Input e output de dados (entrada e saída)                    |
| **java.lang**   | Recursos de linguagem                                        |
| **java.math**   | Operações matemáticas                                        |
| **java.text**   | Recursos de texto                                            |
| **java.util**   | Miscelânea de recursos utilitários                           |
| **javax.swing** | Complemento ao pacote awt                                    |

<br />

<h3>1.1 Criando um Pacote no Eclipse</h3>

Vamos reescrever a Calculadora, utilizando Métodos e Pacotes:

1. Crie um novo Projeto Java no Eclipse (menu: **File 🡪 New 🡪 Java Project**)
2. O nome do projeto será **aula_metodos**, como mostra a figura abaixo:

<div align="center"><img src="https://i.imgur.com/iNtc3aY.png" title="source: imgur.com" /></div>

3. Clique no botão **Finish** para continuar.

4. No lado esquerdo superior, na Guia **Package explorer**, clique com o botão direito do mouse sobre a pasta **src**, como indicado na figura abaixo:

<div align="center"><img src="https://i.imgur.com/sJ8QrDl.png" title="source: imgur.com" /></div>

5. Na sequência, clique na opção **New 🡪 Package**.

<div align="center"><img src="https://i.imgur.com/2qGxWAw.png" title="source: imgur.com" /></div>

6. Na janela **New Java Package**, no item **Name**, acrescente no final do nome do projeto **.calculo**, como mostra a figura abaixo:

<div align="center"><img src="https://i.imgur.com/FnqrcFU.png" title="source: imgur.com" /></div>

7. Clique no botão **Finish** para concluir.

8. A estrutura de pacotes da aplicação ficará igual a figura abaixo:

<div align="center"><img src="https://i.imgur.com/UgcrQhK.png" title="source: imgur.com" /></div>

Observe na imagem acima, que o **pacote1** está com o seu ícone na cor branca porque no momento não foi criada nenhuma Classe dentro do pacote.

No Pacote **calculo**, vamos criar a Classe **Calculadora**:

1. No lado esquerdo superior, na Guia **Package explorer**, clique com o botão direito do mouse sobre o pacote **aula_pacotes.calculo**, como indicado na figura abaixo:

<div align="center"><img src="https://i.imgur.com/UgcrQhK.png" title="source: imgur.com" /></div>

2. Na sequência, clique na opção **New 🡪 Class**.

<div align="center"><img src="https://i.imgur.com/nVzDptB.png" title="source: imgur.com" /></div>

3. Na janela **New Java Class**, no item **Name**, informe o nome da Classe (**Calculadora**), e desmarque a opção: **public static void main(String[] args)**, como mostra a figura abaixo:

<div align="center"><img src="https://i.imgur.com/7l4vDMZ.png" title="source: imgur.com" /></div>

4. Clique no botão **Finish** para concluir.
5. A nova Classe ficará igual a imagem abaixo:

<div align="center"><img src="https://i.imgur.com/P9wSrzF.png" title="source: imgur.com" /></div>

6. Insira o código abaixo na Classe **Calculadora**:

```java
package aula_pacotes.calculo;

public class Calculadora {

	public static float soma(float numero1, float numero2) {
		return numero1 + numero2;
	}

	public static float subtracao(float numero1, float numero2) {
		return numero1 - numero2;
	}

	public static float multiplicacao(float numero1, float numero2) {
		return numero1 * numero2;
	}

	public static float divisao(float numero1, float numero2) {
		return numero1 / numero2;
	}

}
```

10. Salve o arquivo.

Agora, vamos criar a Classe **TestaCalculadora**, para testarmos a Classe **Calculadora**:

1. No lado esquerdo superior, na Guia **Package explorer**, clique com o botão direito do mouse sobre a pasta **src**, como indicado na figura abaixo:

<div align="center"><img src="https://i.imgur.com/sJ8QrDl.png" title="source: imgur.com" /></div>

2. Na sequência, clique na opção **New 🡪 Class**.

<div align="center"><img src="https://i.imgur.com/pqKjoxf.png" title="source: imgur.com" /></div>

3. Na janela **New Java Class**, no item **Package**, altere o nome do Pacote para **aula_pacotes**, no item **Name**, informe o nome da Classe (**TestaCalculadora**), e marque a opção: **public static void main(String[] args)**, como mostra a figura abaixo:

<div align="center"><img src="https://i.imgur.com/XGV1gSD.png" title="source: imgur.com" /></div>

4. Clique no botão **Finish** para concluir.
5. Insira o código abaixo na Classe **TestaCalculadora**:

```java
package aula_pacotes;

import java.util.Scanner;

import aula_pacotes.calculo.Calculadora;

public class TestaCalculadora {

	public static void main(String[] args) {

		Scanner leia = new Scanner(System.in);

		float numero1 = 0, numero2 = 0;

		System.out.println("Digite o primeiro numero: ");
		numero1 = leia.nextFloat();

		System.out.println("Digite o segundo numero: ");
		numero2 = leia.nextFloat();

		// Exibe o Resultado de cada Operação Matemática:
		System.out.println("Soma = " + Calculadora.soma(numero1, numero2));
		System.out.println("Subtração = " + Calculadora.subtracao(numero1, numero2));
		System.out.println("Multiplicação = " + Calculadora.multiplicacao(numero1, numero2));
		System.out.println("Divisão = " + Calculadora.divisao(numero1, numero2));

		// finaliza o Objeto leia
		leia.close();

	}

}
```

👉 Observe no código acima, que a **Classe Calculadora** foi importada (**import aula_pacotes.calculo.Calculadora;**), porque ela se encontra em outro pacote (**aula_pacotes.calculo**). Para executar os Métodos **soma(), subtracao(), multiplicacao() e divisao()**, foi necessário indicar o nome da Classe. **Exemplo:** `Calculadora.soma(numero1, numero2)`

6. Salve o arquivo.
7. Observe que a Classe Calculadora está em um Pacote e a Classe TestaCalculadora está em outro, como mostra a imagem abaixo:

<div align="center"><img src="https://i.imgur.com/yXkxL7r.png" title="source: imgur.com" /></div>

Execute aplicação e veja o resultado:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Código:**

```bash
Digite o primeiro numero: 
20
Digite o segundo numero: 
10
Soma = 30.0
Subtração = 10.0
Multiplicação = 200.0
Divisão = 2.0
```

👉 O Resultado final será o mesmo, entretanto, os Métodos de Cálculo estão implementados na Classe **Calculadora**, enquanto na Classe principal da aplicação (TestaCalculadora), foi implementado apenas as entradas de dados e as chamadas dos Métodos. Quanto aos Pacotes, a Classe Calculadora foi criada em um sub pacote, chamado calculo, enquanto a Classe principal (TestaCalculadora), permanece no pacote principal da aplicação, deixando o projeto e o código mais organizado. 

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/metodos/aula_pacotes" target="_blank"><b>Código fonte</b></a>

<br /><br />

------

## 🔑**Pontos chave:**

1. Um Método é um grupo de código reutilizável que pode ser invocado em qualquer lugar do seu programa;
2. **Um método deve realizar apenas uma tarefa para facilitar os processos de testagem e depuração**;
3. Todo o Método possui um Modificador de Acesso, que determina qual (is) Classes podem chamar o Método;
4. Todo o Método, opcionalmente, pode ter um Modificador de Método, que determina como as classes derivadas podem ou não redefinir ou alterar o método;
5. Um Método pode ter um tipo de retorno (int, float, String, entre outros) ou não retornar nada (void);
6. Um Método pode receber nenhum, um ou mais argumentos que correspondam a diferentes tipos de dados de entrada e  esses dados podem ser processados e/ou utilizados dentro do código do método.
7. Um **Pacote** ou **Package** na tecnologia  Java nada mais é do que um conjunto de classes localizadas na mesma  estrutura hierárquica de pastas, com o objetivo de organizar as Classes  dentro do projeto.

<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>	
