<h1>Optional</h1>



**Optional** é uma Classe que foi implementada no Java 8, que tem o objetivo de  simplificar os códigos, facilitando a vida das pessoas desenvolvedoras.

A principal proposta deste recurso é encapsular o retorno de métodos e informar se um valor do tipo `<T>` (Java Generics) está presente ou ausente.

> **Java Generics** é uma Classe ou Interface genérica, como a Classe Optional por exemplo, que é parametrizada por tipos específicos, ou seja, permitem que tipos (classes e interfaces) sejam parâmetros ao definir Classes, Interfaces e Métodos. 
>
> O tipo específico é definido dentro do diamante `<T>`, onde **T** representa o tipo.  Caso um tipo não seja definido, ou seja, o diamante esteja vazio `<T>` ou com uma interrogação `<?>`, a Classe ou Interface genérica aceitará qualquer tipo de Objeto.
>
> **Exemplo:** `Optional <String> teste`
>
> No exemplo acima foi criado um Objeto da Classe Genérica Optional, chamado **teste**, que armazenará uma String.
>
> A principal vantagem de utilizar Java Generics é evitar conversões de tipos de dados o tempo todo (cast), além de deixar o código mais limpo e intuitivo.

Fazendo uma analogia, o Optional é como uma caixa onde guardamos (encapsulamos) um Objeto, para evitar o erro *NullPointerException*.

<div align="center"><img src="https://i.imgur.com/7JzXM53.png" title="source: imgur.com" /></div>

Sempre que precisamos deste Objeto, utilizamos os Métodos da Classe Optional, que veremos na sequência.

O *Optional* nos ajuda nas seguintes tarefas:

- Evitar os erros do tipo *NullPointerException*;
- Elimina a necessidade da verificação se um Objeto é nulo (null), através do condicional `if (variavel != null)`;
- Permite escrever um código com menos linhas, mais limpo e elegante.

**Sintaxe:**

```java
// Optional com o valor vazio
Optional<String> optional = Optional.empty();

// Valor diferente nulo
Optional<String> optional = Optional.of(palavra[5]);

// Existe a probabilidade do valor ser nulo
Optional<String> optional = Optional.ofNullable(palavra[5]);

```

Como vimos acima, existem 3 Métodos para criar um Optional:

| Método           | Descrição                                                    |
| ---------------- | ------------------------------------------------------------ |
| **empty()**      | Retorna uma instância do `Optional` vazia.                   |
| **of()**         | Retorna um `Optional` com o valor fornecido, mas o valor não pode ser nulo. |
| **ofNullable()** | Se o valor estiver presente, retorna um `Optional` com o valor, caso contrário, retorna um `Optional` vazio. Este é um dos métodos mais indicados para criar um `Optional`, principalmente quando não se tem a certeza de que o Objeto está ou estará presente. |

<br />

<h3>1.1. Principais Métodos  da Classe Optional</h3>

| Método            | Descrição                                                    |
| ----------------- | ------------------------------------------------------------ |
| **filter()**      | Se um valor estiver presente e o valor corresponder ao critério de filtragem, ele retorna um `Optional` com o valor, se não, retorna um `Optional` vazio. |
| **isPresent()**   | Checa se um valor está presente. Se estiver retorna `true`, se não, retorna `false`. |
| **isEmpty()**     | Checa se um valor não está presente. Se não estiver presente retorna `true`, se não, retorna `false`. |
| **get()**         | Se um valor estiver presente, ele retorna o valor, caso contrário, lança a exceção `NoSuchElementException`, logo para usar o `get` é preciso ter certeza de que o `Optional` não está vazio. |
| **ifPresent()**   | Se um valor estiver presente, executa uma ação no valor, caso contrário, não faz nada. |
| **map()**         | Se um valor estiver presente retorna um `Optinal` com o resultado da aplicação da função de mapeamento no valor, caso contrário, retorna um `Optional` vazio. Geralmente utilizamos o Optional em conjunto com as Expressões Lambda. |
| **flatMap()**     | Semelhante ao `map`, se um valor estiver presente, retorna o resultado da aplicação da função de mapeamento no valor, caso contrário retorna um `Optional` vazio. A diferença é que o `flatMap` pode ser aplicado a um mapeamento que também retorna um `Optional`. |
| **orElse()**      | Geralmente utilizado em conjunto com o **método map()** ou com o **método flatMap()**, se o resultado do **método map()** ou do **método flatMap()** for falso, ele retorna o valor definido no parâmetro do método **orElse()**. |
| **orElseGet()**   | Geralmente utilizado em conjunto com o **método map()** ou com o **método flatMap()**, se o resultado do **método map()** ou do **método flatMap()** for falso, retorna o resultado produzido pelo parâmetro. |
| **orElseThrow()** | Geralmente utilizado em conjunto com o **método map()** ou com o **método flatMap()**, se o resultado do **método map()** ou do **método flatMap()** for falso, lança uma exceção informada no parâmetro. |

<br />

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Optional.html" target="_blank"><b>Documentação: Classe Optional</b></a></div>

<div align="left"><img src="https://i.imgur.com/JSfXyzm.png" title="source: imgur.com" width="30px"/> <a href="https://docs.oracle.com/javase/tutorial/java/generics/types.html" target="_blank"><b>Documentação: Java Generics</b></a></div>

<br />


## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 01 - Código sem o Optional

Primeiro vamos criar o código abaixo, que irá causar um erro do tipo **NullPointerException**. Neste código não utilizaremos o **Optional**:

```java
package com.generation.optional01;

public class Optional01 {

	public static void main(String[] args) {
        
		String[] palavras = new String[10];
		String palavra = palavras[5].toLowerCase();
		System.out.println(palavra);
        
	}
}
```

No console será exibido o erro abaixo:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```java
Exception in thread "main" java.lang.NullPointerException
```

Este erro indica que a posição 5 do vetor palavras é nula, porquê o vetor não foi preenchido com nenhum valor.

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/java_optional/optional01_v1" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

Na sequência, vamos reescrever o código implementando o Optional:

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 02 - Implementação do Optional

```java
package com.generation.optional01;

import java.util.Optional;

public class Optional01 {

	public static void main(String[] args) {

		String[] palavras = new String[10];

		Optional<String> checaNulo = Optional.ofNullable(palavras[5]);

		if (checaNulo.isPresent()) {
			String palavra = palavras[5].toLowerCase();
			System.out.print(palavra);
		} else
			System.out.println("A palavra é nula!");
	}

}
```

No console será exibida a mensagem abaixo:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```java
A palavra é nula!
```

Observe que o conteúdo da posição 5 do vetor palavras, foi encapsulado em um Objeto da Classe Optional, chamado **checaNulo**. Na sequência, através do Método boolean **IsPresent()**, verificamos se o Optional possui um conteúdo (diferente de nulo). Caso seja diferente de nulo, o conteúdo será exibido em letras minúsculas, através do Método **toLowerCase()** da Classe String. Caso contrário, uma mensagem ***"A palavra é nula!"*** será exibida.

O Optional é uma forma mais elegante e intuitiva de verificar se um Objeto é nulo. Além disso, oferece outros Métodos, como veremos no próximo exemplo:

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/java_optional/optional01_v2" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 03 - Optional - Métodos I 

Neste exemplo vamos utilizar os Métodos **empty(), get() e IsPresent()**:

```java
package com.generation.optional02;

import java.util.Optional;

public class Optional02 {

	public static void main(String[] args) {

		String[] frases = new String[5];

		frases[2] = "Generation Brasil";
		
		Optional<String> optionalVazio = Optional.empty();
		System.out.println("\n Exibir optionalVazio: " + optionalVazio);
		System.out.println("\n optionalVazio está vazio? " + optionalVazio.isEmpty());

		Optional<String> valor_indice_02 = Optional.of(frases[2]);
		System.out.println("\n Exibir valor_indice_02: " + valor_indice_02);
		System.out.println("\n Obter o conteúdo de valor_indice_02: " + valor_indice_02.get());
		System.out.println("\n valor_indice_02 está presente? " + valor_indice_02.isPresent());

	}

}
```

No console será exibida a mensagem abaixo:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```java
Exibir optionalVazio: Optional.empty

optionalVazio está vazio? true

Exibir valor_indice_02: Optional[Generation Brasil]

Obter o conteúdo de valor_indice_02: Generation Brasil

valor_indice_02 está presente? true
```

Observe que através do com o Método **isEmpty()** verificamos se o Optional **optionalVazio** está realmente vazio, com o Método **get()** acessamos o conteúdo do Optional **valor_indice_02**  e com o Método **isPresent()** verificamos se o Optional **valor_indice_02** possui um Objeto não nulo.

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/java_optional/optional02" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="3%"/>Exemplo 04 - Optional  - Métodos II

No exemplo abaixo vamos utilizar a Classe **Colaborador** e utilizar os Métodos **map(), filter() e orElseThrow()** da Classe **Optional**, em conjunto com uma **Expressão Lambda** para fazer uma busca:

**Classe Colaborador**

```java
package com.generation.optional03.model;

public class Colaborador {

	private Long id;
	private String nome;
	private Float salario;
	
	public Colaborador(Long id, String nome, Float salario) {
		this.id = id;
		this.nome = nome;
		this.salario = salario;
	}
	
	public Long getId() {
		return id;
	}
	public void setId(Long id) {
		this.id = id;
	}
	public String getNome() {
		return nome;
	}
	public void setNome(String nome) {
		this.nome = nome;
	}
	public Float getSalario() {
		return salario;
	}
	public void setSalario(Float salario) {
		this.salario = salario;
	}
	
}

```

**Classe Optional03**

```java
package com.generation.optional03;

import java.util.Optional;

import com.generation.optional03.model.Colaborador;

public class Optional03 {

	public static void main(String[] args) {
				
		Colaborador c1 = new Colaborador(1L, "James Bond", 1000.0f);
		
	    Optional<Colaborador> colaboradorOptional = Optional.of(c1);
	    
	    colaboradorOptional.map(resposta -> resposta.getNome())
	    		.filter(colaboradorNome -> colaboradorNome.startsWith("J"))
	    		.orElseThrow(() -> new RuntimeException("Colaborador não encontrado!"));
	                                                    
	    System.out.println("\nNome do Colaborador: " + colaboradorOptional.get().getNome());
	    
	}

}

```

No console será exibida a mensagem abaixo:

<img src="https://i.imgur.com/V2ReOnx.png" title="source: imgur.com" width="3%"/>**Resultado do Algoritmo:**

```java
Nome do Colaborador: James Bond
```

Observe que através do Método **map()**, criamos um laço condicional, onde se as condições forem satisfeitas, ou seja, o Objeto c1, que está encapsulado no Objeto Optional **colaboradorOptional**, corresponder as condições estabelecidas no Método **filter()**, será exibido o nome do Colaborador através do Método **getNome()**, da Classe **Colaborador**. Caso contrário, será lançada uma Exceção do tipo `RuntimeException` contendo a mensagem: *"Colaborador não encontrado!"*. 

O Método **filter()**, define as condições para que o Atributo nome do colaborador do Objeto c1 seja exibido na tela. No exemplo acima, o nome deve iniciar com a letra ***J***. Para testar esta condição, foi utilizado o Método **startsWith()**, da Classe String.

Para finalizar o método map(), o Método **orElseThrow()** lança a Exceção do tipo `RuntimeException`, caso o Objeto não corresponda a condição do Método **filter()**.

Observe que para exibir no console o nome do Colaborador, é necessário utilizar o Método **get()** para acessar o Objeto **c1**, que está encapsulado dentro do Objeto **colaboradorOptional**, para conseguir executar o Método **getNome()**, da Classe Colaborador. Por isso que descrevemos o Optional como uma caixa, que encapsula um Objeto.

> **Expressões Lambda:** Expressão Lambda é uma  função sem uma classe, então a palavra-chave "this" não se refere a  própria lambda, mas sim a classe na qual foi declarada. Isso distingue de uma classe interna anônima, na qual "this" refere-se a própria classe interna.

<br />

<div align="left"><img src="https://i.imgur.com/bQGvf3h.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/java_optional/optional03" target="_blank"><b>Código fonte do exemplo</b></a></div>

<br />

------

## 🔑**Pontos chave:**

1. **Optional** é uma classe que foi implementada no **Java** 8+, que tem o objetivo de simplificar os códigos, facilitando a vida dos desenvolvedores. 
2. O **Optional** nos ajuda a evitar os erros *NullPointerException*, elimina a necessidade da verificação (if x != null) e também a escreve um código com menos linhas e mais limpo.

<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>	
