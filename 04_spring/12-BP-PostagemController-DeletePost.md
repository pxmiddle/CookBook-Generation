﻿<h1>Projeto 02 - Blog Pessoal - Classe PostagemController - Método Deletar</h1>

O que veremos por aqui:

1. Criar o Método delete(Long id) para excluir uma Postagem no Banco de Dados

<h2>1. O Recurso Postagem</h2>

Nas etapas anteriores, construímos a Classe **PostagemController** e implementamos os Métodos:

- **getAll()**  🡪 Retorna todos os Objetos da Classe Postagem.

- **getById(Long id)** 🡪 Retorna um Objeto específico da Classe Postagem persistidos no Banco de dados. A Postagem é identificada pelo Atributo id.   

- **getByTitulo(String titulo)** 🡪 Retorna  todos os Objetos da Classe Postagem persistidos no Banco de dados, cujo Atributo titulo contenha a String enviada no parâmetro titulo do Método.   

- **Método post(Postagem postagem)** 🡪 Persiste (salva) um novo Objeto da Classe Postagem no Banco de dados

- **Método put(Postagem postagem)** 🡪 Atualiza um Objeto da Classe Postagem persistido no Banco de dados.

<div align="center"><img src="https://i.imgur.com/aKmFiA1.png" title="source: imgur.com" width="50%"/></div>

Vamos finalizar a construção da Classe Controladora com o **Método delete(Long id)**.

<br />

<h2>👣 Passo 01 - Criar o Método delete(Long id)</h2>

Vamos implementar o Método **delete(Long id)** na Classe Postagem Controller. Traçando um paralelo com o MySQL, seria o equivalente a instrução: <code>DELETE FROM tb_postagens WHERE id = id;</code>.

<div align="left"><img src="https://i.imgur.com/lHEatPH.png" title="source: imgur.com" /></div>

**Linha 65:** A anotação **@ResponseStatus** indica que o Método **delete(Long id)**, terá um Status HTTP específico quando a Requisição for bem sucedida, ou seja, será retornado o **HTTP Status NO_CONTENT 🡪 204**, ao invés do **HTTP Status OK 🡪 200** como resposta padrão do Método.

**Linha 66:** A anotação **@DeleteMapping("/{id}")** mapeia todas as Requisições **HTTP DELETE**, enviadas para um endereço específico (**Endpoint**), dentro do Recurso Postagem, para um Método específico que responderá as requisições, ou seja, ele indica que o Método **delete( Long id )**, responderá a todas as requisições do tipo **HTTP DELETE**, enviadas no endereço **http://localhost:8080/postagens/id**, onde **id** é uma **Variável de Caminho** (Path Variable), que receberá o id da Postagem que será Deletada.

**Linha 67:** O Método **delete(@PathVariable Long id)** foi definido com o tipo **void**, porque ao deletar um Objeto da Classe Postagem do Banco de dados, ela deixa de existir, logo não existe um Objeto para ser Retornado. Como configuramos a anotação **@ResponseStatus** com um HTTP Status específico, O Método delete vai apenas inserir na **Resposta da Requisição o HTTP Status NO_CONTENT 🡪 204**, indicando que o Objeto deletado foi apagado e o seu conteúdo não existe mais. Observe que o Método possui um parâmetro do tipo **Long**, chamado **id**.

**@PathVariable Long id:** Esta anotação insere o valor enviado no endereço do endpoint, na Variável de Caminho **{id}**, no parâmetro do Método **delete( Long id )**;

<br />

**Exemplo:**

**http://localhost:8080/postagens/1**

No exemplo acima, o parâmetro **Long id**, do Método **delete( Long id )**, receberá o valor **1** (Id que será procurado na tabela tb_postagens)

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="100px"/> | <div align="left"> **ATENÇÃO:** *Por questões de boas práticas e legibilidade do código, a Variável de Caminho e o Parâmetro do Método delete devem possuir o mesmo nome.* </div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

**Linha 68:** **Optional<img src="https://i.imgur.com/QKIS6Rm.png" title="source: imgur.com" height="20px"/> postagem = postagemRepository.findById(id);:** Cria um **Objeto Optional da Classe Postagem** chamado **postagem**, que receberá o resultado do Método **findById(id)**. Como o Método pode retornar um **Objeto Nulo**, caso ele não seja encontrado, utilizaremos um **Objeto Optional** para encapsular a resposta do Método **findById(id)** e evitar o erro **NullPointerException**. 

**Linhas 69 e 70:**  Através do Laço Condicional **if**, checaremos se o Objeto postagem está vazio (**postagem.isEmpty()**), ou seja, Objeto Nulo. Se o Objeto estiver vazio, lançaremos uma **Exception** contendo o **HTTP Status NOT FOUND 🡪 404** (Não Encontrado!), através da **Classe ResponseStatusException**. Através do comando **throw new ResponseStatusException(HttpStatus.NOT_FOUND);** a Exception será lançada e as próximas linhas de código do Método serão ignoradas.

**Linha 73:** Caso contrário, o Método padrão da Interface JpaRepository **deleteById(Long id)** será executado e o **HTTP Status NO_CONTENT 🡪 204**, HTTP Status padrão do Método, será enviado na Resposta da Requisição, indicando que o Objeto foi Excluído.

Depois de Criar o Método, observe que foram importados mais 3 pacotes, como mostra a imagem abaixo (indicados pelas Setas vermelhas):

<div align="left"><img src="https://i.imgur.com/SzboE1I.png" title="source: imgur.com" /></div>

Para concluir, não esqueça de Salvar o código (**File 🡪 Save All**) e verificar se o Projeto está em execução.

<br />

<div align="left"><img src="https://i.imgur.com/wDz2IzB.png" title="source: imgur.com" width="25px"/> <a href="https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/DeleteMapping.html" target="_blank"><b>Documentação: <i>@DeleteMapping</i></b></a></div>

<div align="left"><img src="https://i.imgur.com/wDz2IzB.png" title="source: imgur.com" width="25px"/> <a href="https://www.baeldung.com/spring-pathvariable" target="_blank"><b>Documentação: <i>@PathVariable</i></b></a></div>

<div align="left"><img src="https://i.imgur.com/wDz2IzB.png" title="source: imgur.com" width="25px"/> <a href="https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/http/ResponseEntity.html#created-java.net.URI-" target="_blank"><b>Documentação: <i>ResponseEntity</i></b></a></div>

<div align="left"><img src="https://i.imgur.com/wDz2IzB.png" title="source: imgur.com" width="25px"/> <a href="https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/http/HttpStatus.html#NO_CONTENT" target="_blank"><b>Documentação: <i>HttpStatus</i></b></a></div>

<div align="left"><img src="https://i.imgur.com/wDz2IzB.png" title="source: imgur.com" width="25px"/> <a href="https://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/CrudRepository.html#deleteById-ID-" target="_blank"><b>Documentação: <i>.deleteById()</i></b></a></div>

<div align="left"><img src="https://i.imgur.com/wMe2uG1.png" title="source: imgur.com" width="3%"/> <a href="https://docs.google.com/document/d/1IQwgepFjSVCsMWiLHCidJyAj3jF2xp5h/edit" target="_blank"><b>Documentação: <i>Optional</i></b></a></div>

<br />

<h2>👣 Passo 02 - Testar no Insomnia</h2>

Agora vamos criar a Requisição para o **delete(Long id)**:

1. Clique com o botão direito do mouse sobre a **Pasta Postagem** para abrir o menu e clique na opção **New Request**.

<div align="center"><img src="https://i.imgur.com/KvRI8b2.png" title="source: imgur.com" /></div>

2. Será criada uma nova Requisição (New Request) dentro da pasta **Postagem**.

   <div align="center"><img src="https://i.imgur.com/CA70WQn.png" title="source: imgur.com" /></div>

3. Dê um duplo clique sobre a nova requisição (**New Request**), informe o nome da requisição (indicado na imagem abaixo na cor amarela) e pressione a tecla **enter** do seu teclado.

<div align="center"><img src="https://i.imgur.com/rZ0KTLu.png" title="source: imgur.com" /></div>

4. Selecione o Método HTTP que será utilizado (**DELETE**) na requisição, indicado na imagem abaixo na cor verde. 

<div align="center"><img src="https://i.imgur.com/qvMhoEx.png" title="source: imgur.com" /></div>

5. Configure a requisição conforme a imagem abaixo:

<div align="center"><img src="https://i.imgur.com/wi2QFdM.png" title="source: imgur.com" /></div>

6. No item marcado em amarelo na imagem acima, informe o endereço (endpoint) da Requisição. A requisição **Deletar Postagem** foi configurada da seguinte maneira:

   - A primeira parte do endereço (**http://localhost:8080**) é o endereço do nosso servidor local. Quando a API estiver na nuvem, ele será substituído pelo endereço da aplicação na nuvem.
   - A segunda parte do endereço é o **endpoint** configurado na anotação ***@RequestMapping***, em nosso caso  **/postagens/**. 
   - A terceira parte (**/3**) é a varável de caminho (**@PathVariable**) id. Informe o id da postagem que você deseja apagar.
   
7. Para testar a requisição, com a aplicação rodando, clique no botão <img src="https://i.imgur.com/sy0V8Nx.png" title="source: imgur.com" width="60px"/>.

8. O resultado da requisição você confere na imagem abaixo:

<div align="center"><img src="https://i.imgur.com/SspTgpZ.png" title="source: imgur.com" /></div>

9. Observe que a aplicação retorna apenas um **HTTP Status 204 🡪 NO_CONTENT** (indicado em verde na imagem acima). Este Status indica que a Requisição foi bem sucedida!, o Objeto foi apagado e o seu conteúdo não existe mais. Observe no Corpo da Resposta que não foi retornado nenhum Objeto (indicado pela seta verde), porque ele foi apagado.

10. Caso o Objeto não seja encontrado, a aplicação retornará o **HTTP Status 404 🡪 NOT FOUND** (Não encontrado), como mostra a figura abaixo (marcado em laranja).

<div align="center"><img src="https://i.imgur.com/HuQst2w.png" title="source: imgur.com" /></div>

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/backend_blogpessoal_v3/tree/09_Classe_PostagemController_delete" target="_blank"><b>Código fonte do projeto</b></a></div>


<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
