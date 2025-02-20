<h1>Java IDE - Eclipse</h1>

O Eclipse IDE (Integrated Development Environment ou Ambiente de Desenvolvimento Integrado) é um editor de código que fornece grande suporte ao desenvolvimento Java, sendo umas das principais IDEs escolhidas quando o assunto é Java.

<div align="center">
  <img src="https://i.imgur.com/5ycLW2b.png" title="source: imgur.com" width="50%"/>
</div>

> Um **Ambiente de Desenvolvimento Integrado (IDE)** é um software para criar  aplicações que combina ferramentas comuns de desenvolvimento em uma única interface de usuário gráfica (GUI). Um IDE geralmente consiste em:
>
> - **Editor de código-fonte**: é um editor de texto que auxilia na criação de código de software por  meio de funcionalidades como destaque da sintaxe com indicadores  visuais, recurso de preenchimento automático específico da linguagem e  verificação de bugs durante a criação.
> - **Automação de compilação local**: são utilitários que automatizam tarefas simples e repetíveis durante a  criação de uma compilação local do software usada pelo desenvolvedor.  São tarefas como compilação de código-fonte em código binário, criação  de pacotes de código binário e execução de testes automatizados.
> - **Debugger**: é um programa usado para testar outros programas e mostrar graficamente a localização do bug no código original.

A **Eclipse IDE for Java Developers** foi projetada para oferecer todo o suporte necessário para o desenvolvimento Java padrão, incluindo algumas ferramentas como: 

* Maven e Gradle, gerenciadores de dependências para projetos que envolvam Frameworks como o Spring;
* Integração ao Sistema de Controle de Versão Git;
* Ferramenta de depuração de código visual para depurar (analisar a execução de código afim de identificar algum erro de lógica) o código;
* Recurso JavaDoc que permite criar automaticamente documentação para classes em nosso aplicativo;

Além do **Eclipse**, existem outras IDE's voltadas para Java:

| IDE                                                          | Descrição                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img src="https://i.imgur.com/TqtTyJh.png" title="source: imgur.com" width="40%"/> | O **NetBeans** é uma IDE gratuita e de código aberto, cuja a principal característica é o amplo  suporte para criação de interfaces para aplicações web, desktop e mobile. |
| <img src="https://i.imgur.com/I2d4eR2.png" title="source: imgur.com" width="50%"/> | O **IntelliJ** IDE é uma das principais IDEs do mercado. Entre as suas principais características, podemos destacar: o Assistente de código, os plugins e o suporte nativo a Linguagem Kotlin, voltada para Mobile. |
| <img src="https://i.imgur.com/sOdL7HU.png" title="source: imgur.com" width="40%"/> | **Visual Studio Code (VSCode)** é um editor de código para desenvolvimento de aplicações web, que oferece suporte a inúmeras linguagens e tecnologias, inclusive Java. Entre as suas principais características, podemos destacar: IDE multiplataforma e os plugins. |

<br />


| <img src="https://i.imgur.com/vVDBDG0.png" title="source: imgur.com" width="200px"/> | <div align="left"> **ALERTA DE BSM:** *Mantenha a Orientação ao Futuro! A IDE oficial deste curso é o Eclipse. Todo o material foi desenvolvido em cima desta IDE, logo se você decidir utilizar outra IDE, você deverá pesquisar como executar todas as tarefas propostas neste treinamento.*</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br />

<div align="left"><img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="25px"/> <a href="https://www.eclipse.org/downloads/" target="_blank"><b>Site Oficial do Eclipse</b></a></div>

<br />

<h2>👣 Passo 1 - Começando a usar o Eclipse IDE</h2>

1. Após concluirmos a instalação do Eclipse IDE, podemos iniciar a ferramenta através da caixa de pesquisa da sua barra de tarefas, ou no menu iniciar do seu sistema operacional.

![Abrindo Elipse IDE](https://i.imgur.com/NlOAFvd.png)

2. Antes de iniciar, o Eclipse IDE solicita que seja criado um *Workspace* (Área de Trabalho) para armazenar configurações de preferências e projetos desenvolvidos. 

<div align="center">
  <img src="https://i.imgur.com/lQJh5bI.png" title="source: imgur.com" />
</div>

3. Mantenha a pasta padrão ou escolha outra de sua preferência, marque a caixa de seleção indicada para sempre usarmos a mesma Workspace e então clique no botão **Launch**.

<div align="center">
  <img src="https://i.imgur.com/rBmLLYI.png" title="source: imgur.com" />
</div>

4. O Eclipse IDE será inicializado e será exibida a Guia Welcome (Guia de Boas Vindas), com alguns recursos como Overview (Exibição das Principais Funcionalidades), Tutorials (Tutoriais), etc. Não usaremos nenhum desses recursos, portanto feche guia clicando no **X** ao lado da palavra Welcome.

![Imagem 13](https://i.imgur.com/iQkkkaR.png)

5. Ao fechar a guia, o aplicativo terá a seguinte visualização:

![Imagem 14](https://i.imgur.com/uUh1mqg.png)

6. Na janela principal, temos 4 grande áreas, como mostra a imagem abaixo:

<div align="center"><img src="https://i.imgur.com/SqViBmk.png" title="source: imgur.com" /></div>

7. A primeira Área é a **Barra de Menu e Ferramentas**, onde constam os menus e ferramentas como Salvar, Salvar Tudo, Executar, entre outras:

![Imagem 14.1](https://i.imgur.com/BmKZRA8.png)

8. A segunda área é chamada **Package Explorer (Explorador de Pacotes)**, que é responsável por exibir e auxiliar na criação dos Pacotes/Projetos Java:

![Imagem 14.2](https://i.imgur.com/pzCxVuT.png)

9. A terceira área é o **Editor de Código** e o **Outline**, que são responsáveis respectivamente por Editar o código Java e exibir os detalhes dos arquivos Java (conteúdo das variáveis e dos métodos), utilizados ao efetuar debug no código. Esse segundo painel é pouco utilizado, portanto você pode fechá-lo clicando no **X** ao lado da palavra **Outline**.

![Imagem 14.3](https://i.imgur.com/FROTHjL.png)

10. A quarta e última área, é a **Área de Output (Área de Saída)**. Nesta área temos a **Aba Console**, responsável por mostrar a execução e a saída (resultado) do nosso código.

![Imagem 14.4](https://i.imgur.com/rQcOZyO.png)

<br />


| <img src="https://i.imgur.com/vVDBDG0.png" title="source: imgur.com" width="200px"/> | <div align="left"> **ALERTA DE BSM:** *Foque na Orientação aos Detalhes! Não se preocupe caso feche uma Aba sem querer, apesar de ser importante você reforçar a sua Orientação aos Detalhes. Todos os painéis podem ser reabertos através do Menu Window.*</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br />

<h2>👣 Passo 2 - Criando seu primeiro projeto Java</h2>

1. Para criar um novo **Projeto Java**, clique no menu **File 🡪 New 🡪 Java Project**.

![Imagem 14.9](https://i.imgur.com/JY5SDmv.png) 

2. Será aberta a janela **New Java Project**, onde iremos escolher o nome do projeto. 

<div align="center">
  <img src="https://i.imgur.com/ioJMm0p.png" title="source: imgur.com" />
</div>

3. O nosso primeiro projeto Java se chamará **helloWorld**. Digite o nome do projeto no item **Project Name** e clique em **Finish** para concluir.

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="80px"/> | <div align="left"> **ATENÇÃO:** Uma boa prática ao nomear os projetos Java é utilizar somente letras minúsculas.</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<div align="center">
  <img src="https://i.imgur.com/cDFPPEq.png" title="source: imgur.com" />
</div>


4. A janela deverá fechar, e voltaremos a tela padrão, onde podemos observar que no Explorador de Pacotes que o nosso projeto foi criado.

![Imagem 18](https://i.imgur.com/RaHDTdk.png)

5. Observe que foi criada uma pasta chamada **src** (source). Esta pasta é a *origem* do nosso projeto, onde todos os pacotes/pastas e arquivos **referentes ao Projeto helloworld** serão criados e organizados. Para criar nosso primeiro pacote, uma pasta para organizar outras pastas e arquivos Java, clique com o botão direito do mouse na pasta **src** e no menu que será aberto, clique na opção **New 🡪 Package**

![Imagem 21](https://i.imgur.com/Rca9AyT.png)

6. Na janela **New Java Package**, no item **Name**, informe o nome do pacote **helloworld**.

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="80px"/> | <div align="left"> **ATENÇÃO:** Uma boa prática ao nomear os pacotes no Java é utilizar somente letras minúsculas.</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<div align="center">
  <img src="https://i.imgur.com/6TQBz3V.png" title="source: imgur.com" />
</div>


7. Observe no Explorador de Pacotes, que o novo pacote foi adicionado ao nosso projeto.

![Imagem 23](https://i.imgur.com/4s0ZpXy.png)

8. Na sequência, vamos criar a nossa primeira classe Java. Clique com o botão direito do mouse sobre o pacote **helloworld** e no menu que será aberto, clique na opção **New 🡪 Class**:

![Imagem 25](https://i.imgur.com/rvEWpe0.png)

9. Na janela **New Java Class**, no item **Name:** informe o nome da Classe: **HelloWorld** (indicado pela seta vermelha), marque a opção **public static void main(String[] args)** - (indicado pela seta azul) e clique no botão **Finish** para concluir.

<div align="center">
  <img src="https://i.imgur.com/ymlJdhn.png" title="source: imgur.com" />
</div>


| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="80px"/> | <div align="left"> **ATENÇÃO:** Uma boa prática ao nomear Classes Java é utilizar o formato PascalCase, onde iniciamos todas as palavras que compõem o nome do projeto com letras maiúsculas.</div> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |


10. De volta a tela padrão, observe no Explorador de Pacotes, que o nosso pacote que antes estava branco, mudou de cor, indicando que existe conteúdo em seu interior. Observe também que a Classe **HelloWorld** está aberta na área de Edição do Código.

![Imagem 27](https://i.imgur.com/52lHXGM.png)

11. Como essa Classe serve apenas para nos familiarizarmos com o Eclipse IDE, dentro das chaves do método **public static void main(String[ ] args)** iremos adicionar o comando `System.out.println("Hello World");`, como mostra a imagem abaixo: 

![Imagem 28](https://i.imgur.com/J2aXiuS.png)

12. Como fizemos uma alteração na classe, podemos notar que ao lado de seu nome existe um **asterisco(*)**, indicando que uma alteração foi feita e que ainda não foi salva. Feito isso, iremos salvar pressionando o atalho **CTRL + S**, ou **clicando no ícone Salvar na Barra de Ferramentas** (indicado em vermelho na imagem):

![Imagem 28.5](https://i.imgur.com/zdkAohy.png)

13. Após salvarmos, o asterisco desaparece indicando que nossa classe está pronta para ser testada com a modificação que fizemos anteriormente.

14. Para executarmos o Projeto, clique no botão <img src="https://i.imgur.com/t28CIT4.png" title="source: imgur.com" width="4%"/>**Run**, na **Barra de Ferramentas** (indicado em vermelho na imagem):

![Imagem 30](https://i.imgur.com/7EvltmK.png)

15. Observe na Área de Saída, na Aba Console, que será exibido o texto: **Hello World**.

![Imagem 31](https://i.imgur.com/ycSFP5J.png)

Parabéns! Você criou seu primeiro projeto Java, contendo: um Pacote, uma Classe Java e executou este programa dentro do **Eclipse IDE**.

## <img src="https://i.imgur.com/gsSDe7P.png" title="source: imgur.com" width="4%"/> Exemplo - Hello World

```java
package helloworld;

public class PrimeiraClasse {

  public static void main(String[] args) {
    System.out.println("Hello World");
  }

}

```

<br />

<div align="left"><img src="https://i.imgur.com/JACNZiR.png" title="source: imgur.com" width="25px"/> <a href="https://github.com/rafaelq80/exemplos_java/tree/main/eclipse/helloWorld" target="_blank"><b>Código fonte</b></a></div>

<br />

<h2>2. Mudando a aparência do Eclipse IDE - Dark Mode</h2>

Por padrão, o Eclipse IDE é fornecido usando a Configuração de Tema: Light (claro), mas se preferir, você pode alternar para um Tema Dark (escuro).

1. Para  isso clique no **Menu Window** e selecione **Preferences**. 

![Imagem 32](https://i.imgur.com/29db3be.png)

2. Na janela que se abre, no canto esquerdo escolha a opção **General** e depois clique em **Appearance**. 

<div align="center">
  <img src="https://i.imgur.com/wmMSIYY.png" title="source: imgur.com" />
</div>

3. Na opção **Theme**, escolha **Dark** e depois em **Apply and Close**

<div align="center">
  <img src="https://i.imgur.com/J0U7xk5.png" title="source: imgur.com" />
</div>

4. Uma mensagem surge pedindo para que você **reinicie o Eclipse IDE**, clique em **Restart**.

![Imagem 36](https://i.imgur.com/yu1X2IJ.png)

5. Ao reiniciar, o seu Eclipse IDE deverá estar com esse tema:

![Imagem 37](https://i.imgur.com/HilLY8l.png)

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🔑**Pontos chave:**

1. O ambiente de desenvolvimento integrado (IDE) é o software ou ferramenta utilizado para elaborar um software.
2. O Eclipse IDE é um dos IDE mais usados para o desenvolvimento de aplicações Java.
3. O IDE possui um terminal incorporado para executar comandos.

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
