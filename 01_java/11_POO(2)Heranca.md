<h1>Programação Orientada a Objetos - Parte 02</h1>
<h2>Herança e Polimorfismo</h2>

Anteriormente, iniciamos nossos estudos sobre os conceitos iniciais da Programação Orientada a Objetos, tais como **Classes, Objetos, Métodos, Atributos e Encapsulamento**. Neste material veremos outros 2 conceitos fundamentais: **Herança e Polimorfismo**. Antes, vamos entender o que é Relacionamento entre Classes:

<h2>1. Relacionamento entre Classes</h2>

**Os Relacionamentos entre classes no Java** definem os Relacionamentos especiais entre os diferentes tipos de classes.

No exemplo abaixo, existe uma relação especial entre uma classe chamada Veículo e uma classe chamada Carro: Um Carro é um tipo de Veículo, como mostra a figura abaixo:

```mermaid
classDiagram
Veiculo <-- Carro: é um tipo de
```

No próximo exemplo, também existe um tipo diferente de relacionamento entre as classes Carro, Motor e Roda. Um Carro é compostos por Motor e Roda, como mostra a figura abaixo:

```mermaid
classDiagram
Carro *-- Motor : é composto por
Carro *-- Roda : é composto por
```

Quando projetamos um aplicativo, precisamos explorar os tipos de relacionamentos entre as classes, porque os relacionamentos nos ajudam de várias maneiras.

Por exemplo, suponha que em um aplicativo, temos classes com comportamentos comuns (métodos), então podemos economizar esforço colocando os comportamentos comuns (métodos) dentro de uma única Classe, chamada de superclasse e na sequência poderemos criar outras Classes que herdarão estes Métodos em comum.

Ou ainda, Suponha que algumas classes não estejam relacionadas entre si, então podemos atribuir diferentes programadores para implementar cada uma delas, sem nos preocuparmos que uma delas terá que esperar pela outra. 

Os relacionamentos entre as classes nos ajudam a entender como os objetos em um programa trabalham em conjunto e se comunicam entre si.

<h3>1.1. Tipos de relacionamento entre classes em Java</h3>

Existem três tipos de relacionamentos mais comuns entre classes em Java que são os seguintes:

- Herança ("Is-A") - É um
- Dependência (“Use-A”) - Usa um
- Associação (“Has-A”) - Tem um

A associação é ainda classificada em 2 categorias:

- Agregação 

- Composição

Veja o resumo no Organograma abaixo:

<div align="center"><img src="https://i.imgur.com/UvL4z36.png" title="source: imgur.com" /></div>



<h4>1.1.1. Relação de Herança</h4>

A herança estabelece um relacionamento entre uma classe mais genérica e abstrata (conhecida como superclasse) e uma classe mais especializada (conhecida como subclasse).

Em outras palavras, define o relacionamento entre duas classes em que uma classe "estende" outra classe, ou simplesmente cria um Relacionamento do tipo **É-Um** (Is-A).

```mermaid
classDiagram
Pessoa <|-- Professor : É uma
Pessoa <|-- Aluno : É uma
```

<h4>1.1.2. Relação de Dependência</h4>

Quando criamos um objeto de uma classe dentro de um método de outra classe, esse relacionamento é chamado **de relacionamento de dependência em Java**, ou simplesmente relacionamento **Usa-Um** (Use-A).

Em outras palavras, quando um método de uma classe usa um objeto de outra classe, ele é chamado de dependência em Java. É o relacionamento mais óbvio e mais geral em java.

```mermaid
classDiagram
Produto <.. Carrinho : Depende de
```

No Diagrama acima, em um aplicativo de comércio eletrônico, a classe Carrinho depende da classe Produto porque a classe Carrinho usa a classe Produto como parâmetro para uma operação de adição de itens. 

Esse tipo de Relacionamento deve ser evitado devido ao alto grau de acoplamento gerado pela dependência.

<h4>1.1.3. Relacionamento de Associação</h4>

A associação é outro tipo de relacionamento fundamental entre classes, que é informalmente conhecido como relacionamento “**Tem-Um**” (Has-A).

Quando um objeto de uma classe é criado como Atributo de uma outra classe, ele é chamado **de relacionamento de associação em java** ou simplesmente um Relacionamento do tipo Tem-Um.

```mermaid
classDiagram
Aluno <-- Professor : Tem um ou mais
```

Neste tipo de relacionamento é importante definir também as cardinalidades, ou seja, o numero de Objetos que podem se relacionar com outros Objetos. Existem basicamente 3 tipos de cardinalidades:

- **One to One:** Um Objeto tem relação com apenas Nenhum ou Um Objeto;
- **One to Many / Many to One:** Um Objeto tem relação com Nenhum, Um ou Mais Objetos;
- **Many to Many:** Muitos Objetos tem relação com Muitos Objetos.

Existem dois tipos de relacionamento de Associação especiais, que são os seguintes:

- Agregação
- Composição

**Agregação:** Uma agregação é uma forma especial de associação que representa um relacionamento de propriedade entre dois objetos, ou seja, dois objetos agregados têm seus próprios ciclos de vida, mas um dos objetos é o proprietário do relacionamento Tem-Um. 

O objeto proprietário é chamado de objeto agregador e sua classe é chamada de classe agregadora. A classe agregadora tem uma referência a outra classe e é a proprietária dessa classe. Ter seu próprio relacionamento significa que destruir um objeto não afetará outro objeto.

```mermaid
classDiagram
Departamento o-- Professor : contém
```

No exemplo acima, um Objeto Departamento contém diversos Objetos Professor e ele é o proprietário do Relacionamento. Os Objetos Professor continuam existindo mesmo que o Objeto Departamento seja destruído.

As *palavras chaves* usadas para identificar uma agregação são: *"consiste em", "contém", "é parte de"*.

**Composição :** Uma composição é uma forma especial e mais restritiva de agregação. Ele também representa o relacionamento Tem-Um em que um objeto não pode existir por conta própria. O “todo” é realmente dependente da “parte”.

Em outras palavras, dois objetos compostos não podem ter seu próprio ciclo de vida. Ou seja, um objeto composto não pode existir por conta própria. Se um objeto composto for destruído, todas as suas partes também serão excluídas. Veja o exemplo abaixo:

```mermaid
classDiagram
Universidade *-- Departamento : é composta por
```

Por exemplo, uma Universidade é composta por vários Departamentos. Um Departamento é parte de uma Universidade e não pode existir sem a existência da Universidade, assim como nenhum Departamento pode pertencer a duas Universidades diferentes. Se o Objeto Universidade for destruído, todos os Objetos Departamentos serão destruídos automaticamente.

<h3>Como decidir que tipo de relacionamento precisamos?</h3>

Os relacionamentos mais importantes ou mais utilizados no dia a dia são o relacionamento É-Um (Herança) e o relacionamento Tem-Um (Associação). A melhor maneira de decidir que tipo de relacionamento devemos criar é a seguinte:

1. Se o seu problema for definido com a frase: "*O Objeto A é um tipo do Objeto B*", então você deve usar o relacionamento de Herança. **Exemplo:** "*Um cachorro é um Pet*". Não podemos dizer “*Um Cachorro tem um Pet*”, pois não faz o menor sentido. Então, neste caso, vamos criar uma superclasse chamada Pet e uma subclasse derivada chamada Cachorro.

```mermaid
classDiagram
Pet <|-- Cachorro : É um
```

2. Por outro lado, se o seu problema for definido com a frase: "*O Objeto A tem um Objeto B*", então você deve usar o relacionamento de Associação. **Exemplo:**  “*Um Pet tem uma Raça*”. Não podemos dizer: “*Um Pet é uma Raça*”. Esta afirmação não faz o menor sentido. Então, neste caso, vamos criar uma associação entre a Classe chamada Pet e a Classe derivada chamada Cachorro.

```mermaid
classDiagram
Raca <-- Pet : Tem uma
```

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="80px"/> | <p align="justify"> **IMPORTANTE:** Neste primeiro momento, iremos focar na Relação de Herança. </p> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br />

<h2>2. Herança</h2>

O que torna a Orientação a Objetos única é o **conceito de herança**. **Herança** é um mecanismo que permite que características comuns a diversas classes sejam fatoradas de uma classe base, ou **superclasse**, ou seja, permite uma Classe herdar todos os Atributos e Métodos de outra Classe. 

<div align="center"><img src="https://i.imgur.com/2T7wxZN.png" title="source: imgur.com" /></div>

Analisando a imagem acima: 

- Considere **capacidade** como um atributo da **Classe Transporte**, que indica a quantidade de pessoas que o transporte em questão pode transportar.
- Os atributos **numero de rodas** e **velocidade** (KM/h) como atributos da **Classe Terrestre**.
- Os atributos **cor, número de portas, placa e marcha** como atributos da **Classe Automóvel**.
- A imagem acima apresenta um exemplo de Herança, onde:
  - As **Classes Aquático, Terrestre e Aéreo** herdam a **Classe Transporte**.
  - A **Classe Barco** herda a **Classe Aquático**.
  - A **Classe Automóvel** herda a **Classe Terrestre**.
  - A **Classe Avião** herda a **Classe Aéreo**.

A herança é uma forma de reutilização de software em que novas classes são criadas a partir das classes existentes, absorvendo todos os seus atributos e métodos, além de adicionar novos recursos que as novas classes exigem. A partir de uma **classe base**, outras classes podem ser especificadas e cada classe derivada ou **subclasse** apresenta as características (estrutura e métodos) da **superclasse**, além de acrescentar o que for definido como particularidade da subclasse. Cada **subclasse** também se torna uma candidata a ser uma **superclasse** para alguma subclasse futura

Observando o exemplo acima:

- A **Classe Transporte** possui um **atributo chamado capacidade**.
- Como a **Classe Aquático** herda a **Classe Transporte**, pode-se dizer que ela também possui o **atributo capacidade**.
- A **Classe Barco**, como herda a **Classe Aquático**, também possui o **atributo capacidade**.

Abaixo, vemos o Diagrama de Classes do exemplo acima:

<img src="https://i.imgur.com/vGDOChv.png" title="source: imgur.com" width="3%"/>**Exemplo 01 - Diagrama de Classes** 

```mermaid
classDiagram
class Transporte {
- capacidade: int  
}
class Aereo {
  
}
class Terrestre {
- numero de rodas: int  
- velocidade: float 
}
class Aquatico {
  
}
class Aviao {
  
}
class Automovel {
- cor: String
- numero de portas: int
- placa: String
- marcha: int
}
class Barco {
  
}
Transporte <-- Aquatico
Transporte <-- Terrestre
Transporte <-- Aereo
Aquatico <-- Barco
Terrestre <-- Automovel
Aereo <-- Aviao
```

<h3>2.1. Tipos de Herança</h3>

Existem basicamente 2 tipos de herança:

- **Herança Simples:** Cada classe pode ter apenas uma superclasse. Na linguagem Java usa-se a palavra reservada **extends** para declarar que uma classe é herdeira de outra.
- **Herança Múltipla:** É a capacidade de uma classe possuir mais de uma superclasse e herdar os atributos e métodos
  de todas as superclasses. Java não implementa Herança Múltipla nativamente, como a Linguagem C++, por exemplo. Para simular a herança múltipla em Java, usa-se **Interfaces**, que veremos mais adiante.

<h3>2.2. Herança em Java</h3>

**Sintaxe:**

<div align="center"><img src="https://i.imgur.com/LlHR3A0.png" title="source: imgur.com" /></div>

<br />

<h4>2.2.1 Modificadores de Acesso</h4>

As Classes possuem apenas 2 modificadores de acesso:

| **Modificador** | **Descrição**                                                |
| --------------- | ------------------------------------------------------------ |
| **padrão**      | Uma Classe padrão (identificado pela ausência de modificadores) poderá ser acessada por todas as Classes que estiverem **no mesmo pacote**. |
| **public**      | Uma Classe public poderá ser acessado por qualquer classe em qualquer pacote. |

<br />

<h4>2.2.2 Modificadores Non-Access</h4>

As Classes possuem 2 modificadores de Classes:

| Modificador  | Descrição                                                    |
| ------------ | ------------------------------------------------------------ |
| **abstract** | Uma Classe Abstrata não pode ser usada para criar objetos, ou seja, para acessar uma Classe Abstrata, ela deve ser herdada por outra Classe. |
| **final**    | Uma Classe final não pode ser herdada por outras Classes.    |

***\*Observações importantes:\****

- Uma Classe nunca poderá ser abstract e final simultaneamente;
- Uma Classe Abstrata nunca poderá ser instanciada.

<br />

<h4>2.2.3 A palavra reservada extends</h4>

A palavra reservada **extends** - indica que uma Classe está sendo criada como uma herança (extensão) de uma classe existente.

A **Classe existente** é a superclasse, classe base ou classe progenitora.

A **Nova classe** é a subclasse, classe derivada ou classe filha.

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://www.w3schools.com/java/java_modifiers.asp" target="_blank"><b>Documentação: Modificadores de Classes</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://www.w3schools.com/java/ref_keyword_extends.asp" target="_blank"><b>Documentação: Palavra reservada extends</b></a></div>


<br />

<h3>2.3 O Método Construtor da Subclasse</h3>

O Método Construtor de uma Subclasse utiliza o Método super() **que tem a função de chamar o Método Construtor da Superclasse**. Ele sempre é chamado e deve ser o primeiro item dentro do Método Construtor da Subclasse. 

No Método super() devem ser passados como parâmetros todos os Atributos da Superclasse. Os Atributos específicos da Subclasse devem ser mantidos no Método Construtor da Subclasse.

<br />

<h3>2.4 A palavra reservada super</h3>

Além do Método super(), existe também a palavra reservada **super**, que faz referência aos Objetos da Superclasse, semelhante a palavra reservada **this**, que faz referência aos Objetos da própria Classe.

A palavra reservada **super** e usada para chamar Métodos da Superclasse. O uso mais comum da palavra reservada super é eliminar a confusão entre superclasses e subclasses que possuem métodos com o mesmo nome.

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/tutorial/java/IandI/super.html" target="_blank"><b>Documentação: Método super()</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://www.w3schools.com/java/ref_keyword_super.asp" target="_blank"><b>Documentação: Palavra reservada super</b></a></div>

<br /><br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 01 - Implementação em Java 

**Classe Transporte**

```java
package meios_transporte;

public class Transporte {

	private int capacidade;

	public Transporte(int capacidade) {
		this.capacidade = capacidade;
	}

	public int getCapacidade() {
		return capacidade;
	}

	public void setCapacidade(int capacidade) {
		this.capacidade = capacidade;
	}
	
	public void visualizar() {
		
		System.out.println("\n\n************************************************************");
		System.out.println("Dados do Meio de Transporte:");
		System.out.println("****************************************************************");
		System.out.println("Capacidade (número de passageiros: " + this.capacidade);
		
	}
}
```

A Classe Transporte (Superclasse), foi criada com apenas um Atributo (capacidade), conforme o Diagrama de Classes acima. Também foi criado o Método Construtor, os Métodos Get e Set do Atributo e o Método visualizar para exibir os dados do Objeto na tela.

**Classe Terrestre**


```java
package meios_transporte;

public class Terrestre extends Transporte {

	private int numeroRodas;
	protected float velocidade;

	public Terrestre(int capacidade, int numeroRodas, float velocidade) {
		super(capacidade);
		this.numeroRodas = numeroRodas;
		this.velocidade = velocidade;
	}

	public int getNumeroRodas() {
		return numeroRodas;
	}

	public void setNumeroRodas(int numeroRodas) {
		this.numeroRodas = numeroRodas;
	}

	public float getVelocidade() {
		return velocidade;
	}

	public void setVelocidade(float velocidade) {
		this.velocidade = velocidade;
	}

    @Override
	public void visualizar() {

		super.visualizar();
		System.out.println("Número de rodas: " + this.numeroRodas);
		System.out.println("Velocidade: " + this.velocidade);

	}
}

```

A Classe Terrestre (Subclasse), foi criada como Herança da Classe Transporte (**extends Transporte**), com dois Atributos (**numeroRodas** e **velocidade**), conforme o Diagrama de Classes acima. Além disso, também foram criados o Método Construtor, os Métodos Get e Set dos Atributos e o Método visualizar para exibir os dados do Objeto na tela. 

Observe que:

- O Atributo velocidade foi definido como **protected**, porque precisaremos ter acesso ao Atributo através da Classe Automovel.
- Nos parâmetros do Método Construtor foi adicionado o Atributo **capacidade**, da Classe Transporte. 
- No corpo do Método Construtor foi adicionado o Método **super** para acessar os Atributos da Classe Transporte (**super(capacidade)**). 
- No Método visualizar foi adicionado o Método **super** para executar o Método **visualizar()** (**super.visualizar()**), da Classe Transporte, para listar os dados dos atributos da Classe Transporte.

**Classe Automovel**

```java
package meios_transporte;

public class Automovel extends Terrestre{

	private String cor;
	private int numeroPortas;
	private String placa;
	private int marcha;
	
	public Automovel(int capacidade, int numeroRodas, float velocidade, String cor, int numeroPortas, String placa, int marcha) {
		super(capacidade, numeroRodas, velocidade);
		this.cor = cor;
		this.numeroPortas = numeroPortas;
		this.placa = placa;
		this.marcha = marcha;
	}

	public String getCor() {
		return cor;
	}

	public void setCor(String cor) {
		this.cor = cor;
	}

	public int getNumeroPortas() {
		return numeroPortas;
	}

	public void setNumeroPortas(int numeroPortas) {
		this.numeroPortas = numeroPortas;
	}

	public String getPlaca() {
		return placa;
	}

	public void setPlaca(String placa) {
		this.placa = placa;
	}
	
	public int getMarcha() {
		return marcha;
	}

	public void setMarcha(int marcha) {
		this.marcha = marcha;
	}

    @Override
	public void visualizar() {

		super.visualizar();
		System.out.println("cor: " + this.cor);
		System.out.println("Número de portas: " + this.numeroPortas);
		System.out.println("Placa: " + this.placa);
		System.out.println("Marcha: " + this.marcha);
		
	}
}
```

A Classe Automovel (Subclasse), foi criada como Herança da Classe Terrestre (**extends Terrestre**), com os Atributos (**cor, numeroPortas, placa e marcha**), conforme o Diagrama de Classes acima. Além disso, também foram criados o Método Construtor, os Métodos Get e Set dos Atributos e o Método visualizar para exibir os dados do Objeto na tela. 

Observe que:

- No Método Construtor foram adicionados os Atributos **capacidade**, da Classe Transporte, e **numeroRodas**, da Classe Terrestre, nos parâmetros do Método. 
- No corpo do Método Construtor foi adicionado o Método **super** para acessar os Atributos da **Classe Terrestre** e da **Classe Transporte**, que foram herdados na Classe Terrestre (**super(capacidade, numeroRodas, velocidade)**). 
- No Método visualizar também foi adicionado o Método **super** para executar o Método **visualizar()** (**super.visualizar()**), da Classe Terrestre, para listar os dados dos atributos das Classes Terrestre e Transporte.

**Classe TestaTransporte**

```java
package meios_transporte;

public class TestaTransporte {

	public static void main(String[] args) {

		Automovel aut1 = new Automovel(5, 4, 0.0f, "Verde", 4, "EBN-0301", 0);
		
		aut1.visualizar();

	}

}
```

Na Classe TestaTransporte, foi instanciado uma Objeto da Classe Automovel. Observe que devido as Heranças, o Objeto da Classe Automovel possui 7 parâmetros: 

- capacidade (herdado da Classe Transporte)
- numeroRodas e velocidade (Herdado da Classe Terrestre)
- cor, numeroPortas, placa e marcha (Atributos da Classe Automovel)

Abaixo, você confere o resultado do código no Console:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```
*********************************************************************
Dados do Meio de Transporte:
*********************************************************************
Capacidade (número de passageiros: 5
Número de rodas: 4
Velocidade: 0.0
cor: Verde
Número de portas: 4
Placa: EBN-0301
Marcha: 0
```

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/heranca_polimorfismo/meios_transporte" target="_blank"><b>Código fonte</b></a></div>

<br /><br />


> **Dicas sobre Herança:**
>
> 1. Sempre coloque os métodos e atributos comuns para todas as Subclasses na **Superclasse**
> 2. Use herança para modelar uma relação de “estar contido em”, ou seja, **um objeto da Subclasse é um objeto da Superclasse**
> 3. Não use herança a menos que todos ou a maioria dos métodos herdados da Superclasse façam sentido na Subclasse

<br />

<h2>3. Polimorfismo</h2>

O poliformismo deriva da palavra polimorfo, que significa multiforme, ou que pode variar a forma.

Para a POO, polimorfismo é a habilidade de objetos de classes diferentes responderem a mesma mensagem de
diferentes maneiras, ou seja, várias formas de responder à mesma mensagem. O Polimorfismo é a capacidade de um objeto decidir que método aplicar a si mesmo, embora a mensagem possa ser a mesma, os objetos podem responder diferentemente.

**Veja as imagens abaixo:**

Um dono de uma fábrica de brinquedos solicitou que seus engenheiros criassem um mesmo controle remoto para todos
os brinquedos de sua fábrica. A única restrição era que cada brinquedo atendesse aos comandos específicos definidos pelo controle.

<div align="center"><img src="https://i.imgur.com/NM8RVg5.png" title="source: imgur.com" /></div>

Assim quando o brinquedo recebe o sinal MOVER, ele se move de acordo com a sua função:

- Para o avião, mover significa VOAR;
- Para o barco significa NAVEGAR, e
- Para o automóvel CORRER.

<div align="center"><img src="https://i.imgur.com/KnwNIwl.png" title="source: imgur.com" /></div>

Observe que os brinquedos respondem ao mesmo sinal  de formas diferentes. O Polimorfismo permite que diferentes objetos (avião, barco, automóvel) respondam uma mesma mensagem (mover) de formas diferentes (voar, navegar e correr).

<h3>3.1. Como funciona na prática?</h3>

- Ao enviar uma mensagem que pede para uma **subclasse** aplicar um **método** usando certos parâmetros, a subclasse verifica se ela tem ou não um método com esse nome e exatamente com os mesmos parâmetros. 
- Se tiver, usa-o.
- Caso contrário: a **superclasse** torna-se responsável pelo processamento da mensagem e procura por um método com esse nome e esses parâmetros. 
- Se encontrar, chama esse método.

<br />

<h3>3.2. Tipos de Polimorfismo</h3>

O Polimorfismo pode ser classificado de duas maneiras:

<h4>3.2.1. Polimorfismo de Sobrecarga (Sobrecarga de Método)</h4>

Sobrecarregar métodos significa ter vários métodos com nomes iguais, mas com as assinaturas diferentes, dentro de uma mesma Classe. Veja o exemplo abaixo:

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 02: Polimorfismo de Sobrecarga

```java
public class Transporte {

	private int capacidade;

    /*Método Construtor com parâmetros*/
	public Transporte(int capacidade) {
		this.capacidade = capacidade;
	}
    
    /*Método Construtor sem parâmetros*/
    public Transporte() {	}
    
}
```

Observe que no exemplo acima temos dois Métodos Construtores, com o mesmo nome (Transporte), na mesma Classe (Transporte), entretanto com as assinaturas diferentes (um possui parâmetros e o outro não possui parâmetros).

O **polimorfismo de sobrecarga** normalmente acontece sobre os **Métodos Construtores**, pois é comum para uma classe ter várias maneiras de instanciar um Objeto, como vemos no exemplo acima.

O construtor apropriado é chamado comparando a quantidade, os tipos e a ordem dos parâmetros especificados na assinatura do construtor com a quantidade, os tipos e a ordem dos parâmetros especificados na definição de cada construtor.

<br />

<h4>3.2.2. Polimorfismo de Sobreposição (Sobrescrita de Método)</h4>

O ato de sobrescrever um método ou propriedade significa dar uma nova forma ao mesmo, uma nova versão. Em Java, a  **Sobrescrita de Métodos** seria **criar um novo Método na Classe filha contendo a mesma assinatura e o mesmo tipo de retorno do Método Sobrescrito**. (Override). 

Não confunda **Método Sobrescrito** com **Método Sobrecarregado**. Método Sobrecarregado **permite que Métodos com o mesmo nome e com as assinaturas diferentes, coexistam em uma mesma Classe**.

A **Sobrescrita** está diretamente relacionada à orientação a objetos, mais especificamente com a herança. Com a **sobrescrita**, conseguimos especializar os **métodos** herdados das superclasses, alterando o seu comportamento nas subclasses por um comportamento mais específico.

Para indicar que um Método foi sobrescrito, utilizamos a anotação **@Override** (opcional).

> **Anotação:** Anotações são metadados que podem ser inseridos diretamente no código, para  “configurar” determinados recursos que antes deveriam ser feitos em  arquivos separados como, por exemplo, no XML. 
>
> **Metadados:** Metadados, ou Metainformação, são dados sobre outros dados. Um  item de um metadado pode dizer do que se trata aquele dado, geralmente  uma informação inteligível por um computador. Os metadados facilitam o  entendimento dos relacionamentos e a utilidade das informações dos  dados.

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 03: Polimorfismo de Sobrescrita

O Método **visualizar()** da Classe Transporte, está implementado da seguinte forma:

```Java
	public void visualizar() {
		
		System.out.println("\n\n************************************************************");
		System.out.println("Dados do Meio de Transporte:");
		System.out.println("****************************************************************");
		System.out.println("Capacidade (número de passageiros: " + this.capacidade);
		
	}
```

O Método **visualizar()** da Classe Terrestre, foi reescrito da seguinte forma:

```java
	@Override
	public void visualizar() {

		super.visualizar();
		System.out.println("Número de rodas: " + this.numeroRodas);
		System.out.println("Velocidade: " + this.velocidade);

	}
```

O Método **visualizar()** da Classe Automovel, foi reescrito da seguinte forma:

```java
	@Override
	public void visualizar() {

		super.visualizar();
		System.out.println("cor: " + this.cor);
		System.out.println("Número de portas: " + this.numeroPortas);
		System.out.println("Placa: " + this.placa);
		System.out.println("Marcha: " + this.marcha);
		
	}
```

Observe que as assinaturas dos 3 Métodos são as mesmas, entretanto o **Método visualizar() das 3 Classes** possuem implementações diferentes, porquê exibem os Atributos das Classes Herdadas e os seu próprios Atributos.

No exemplo acima, para que o Método **visualizar()** funcione diferente nas **Classes Terrestre e Automovel**, ele precisou ser sobrescrito, porque as **Classes Terrestre e Automovel não possuem acesso direto às variáveis de instância privadas da Superclasse**, ou seja, esse método não pode alterar ou acessar diretamente a variável de instância. Por isso eles executam o Método **super.visualizar()**, para receber os Atributos das Classes Herdadas.

Um ponto de atenção importante em relação a sobrescrita é que um **método redefinido em uma subclasse** com o **mesmo nome** e **mesma lista de parâmetros** que o **método em uma de suas classes antecessoras**, automaticamente oculta o método da classe ancestral (superclasse) a partir da subclasse, ou seja, ele passa a usar o Método da subclasse.

<br />

------

## 🔑**Pontos chave:**

1. **Os Relacionamentos entre classes no Java** definem os Relacionamentos especiais entre os diferentes tipos de classes. 
2. A Herança é um tipo de Relacionamento entre Classes no Java e uma das maiores vantagens da Programação Orientada a Objetos, permitindo que o código seja reutilizado. Em Java, é possível herdar **atributos** e **comportamentos** (**métodos**) de uma classe para outra. 

3. **Herança Simples:** Cada classe pode ter apenas uma superclasse. Na linguagem Java usa-se a palavra reservada **extends** para declarar que uma classe é herdeira de outra.
4. **Herança Múltipla:** É a capacidade de uma classe possuir mais de uma superclasse e herdar os atributos e métodos
   de todas as superclasses. Java não implementa Herança Múltipla nativamente.
5. O Polimorfismo é considerado um dos recursos mais importantes da Programação Orientada a Objetos, permitindo que uma ação seja executada de diferentes maneiras, fornecendo implementações variadas para métodos e interfaces. A palavra **polimorfismo** significa adquirir muitas formas ou assumir funções diferentes. 
6. **Polimorfismo de Sobrecarga:** Permite que um método de determinado nome tenha comportamentos distintos, em função de diferentes parâmetros que ele recebe. Cada método difere no número e no tipo de parâmetros.
7. **Polimorfismo de Sobreposição:** É a redefinição de métodos em classes descendentes, ou seja, um método de uma classe filha com o mesmo nome de um método de uma classe mãe irá sobrepor esse último. O método redefinido tem precedência em relação a chamadas de método nos objetos da subclasse.

<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
