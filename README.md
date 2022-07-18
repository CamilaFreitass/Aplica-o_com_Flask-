<h1>Criando uma aplicação web com Flask</h1>

> Status: Developing ⚠️

<h3>Esse projeto faz parte do curso da Alura, onde desenvolvemos uma aplicação com Flask, mais especificamente um website chamado Jogoteca. A ideia desse projeto é aprender mais sobre Flask que é um framework, contudo também vamos interagir com HTML e CSS.</h3>


#### Tecnologias utilizadas:


<table>
  <tr>
    <td>Python</td>
    <td>Flask</td>
    <td>HTML</td>
    <td>CSS</td>
    <td>Bootstrap</td>
  </tr>
  <tr>
    <td>3.10.2</td>
    <td>2.0.2</td>
    <td>5.0</td>
    <td>3.0</td>
    <td>5.1.x</td>
  </tr>
</table>

Além disso, a [Documentação do Flask](https://flask.palletsprojects.com/en/2.0.x/) auxiliou muito no desenvolvimento desse projeto. E a IDE utilizada foi o [PyCharm](https://www.jetbrains.com/pycharm/download/#section=windows).

*******

<h3>O que eu aprendi construindo esse projeto?</h3>

 * [O que é Flask;](#oqueeFlask)
 * [Como instalar e começar a utilizar o Flask;](#comoinstalar&utilizar)
 * [Dando início a aplicação;](#dandoinicioaaplicacao)
 * [Criando a primeira rota;](#criandoaprimeirarota)
 * [Fazendo rodar a aplicação;](#fazendorodaraaplicacao)
 * [Começando a estruturar aplicação com HTML;](#estruturaraplicacao)
 * [Conectando o arquivo Python com arquivo HTML;](#pythoncomhtml)
 * [Como colocar código Python dentro do HTML;](#pythonnohtml)
 * [Como fazer uma estrutura *for* dentro do HTML;](#fordentrohtml)
 * [Utilizando estrutura de classe e orientação objeto;](#classeeobjeto)
 * [Jinja2;](#jinja2)
 * [Acrescentando mais uma rota;](#acrescentandorota)
 * [Método *post* em requisição HTTP;](#metodopostemrequisicaohttp)
 * [Helper *request* dentro de uma rota para capturar as informações do formulário;](#helperrequest)
 * [Debugger;](#debugger)
 * [Função *return redirect*;](#oqueeFlask)
 
*******

<div id='oqueeFlask'/> 

<h4>O que é o Flask:</h4>

O Flask é um *microframework* que possibilita criar uma aplicação web de forma rápida e eficiente. Tendo como principais características simplicidade, rapidez e eficiência. O Flask tem apenas o essencial, porém conforme a necessidade ou desejo do desenvolvedor, ele é capaz de fazer conexões com bibliotecas que poderão suprir as necessidades do projeto. 

<div id='comoinstalar&utilizar'/> 

<h4>Como instalar e começar a utilizar o Flask:</h4>

Para instalar o Flask basta digitar o seguinte comando no terminal:

`pip instal flask=2.0.2`

**obs:** nesse caso estamos especificando a versão do Flask, caso não seja especificada no comando a versão, será instalada a versão mais atualizada do Flask. 

Próximo passo é iniciar o arquivo Python com o seguinte comando:

`from flask import Flask`

<div id='dandoinicioaaplicacao'/>

<h4> Dando início a aplicação:</h4>

Para dar início a aplicação é necessário criar uma variável `app=`, chamando a função `Flask()` e dentro da função *Flask* colocar (`__name__`). Da seguinte forma:

`app=Flask(__name__)`

<div id='criandoaprimeirarota'/>

<h4>Criando a primeira rota:</h4>

Para criar uma rota utilizamos `@app.route`, em seguida nomeamos a rota `('/inicio')` e criammos uma função dentro dessa rota `def ola():`. Da seguinte forma:
```
@app.route('inicio/')
def ola():```
   return'<h1>Olá Mundo!</h1>'
```
<div id='fazendorodaraaplicacao'/>
<h4>Fazendo rodar a aplicação:</h4>

Para fazermos rodar a aplicação temos que terminar o código com:

`app.run()`

<div id='estruturaraplicacao'/>
<h4>Começando a estruturar a aplicação com HTML:</h4>

Para dar estrutura a aplicação precisamos utilizar HTML. Nesse caso vamos utilizar um arquivo pronto disponibilizado pelo curso da Alura.

<div id='pythoncomhtml'/>
<h4>Conectando o arquivo Python com arquivo HTML:</h4>

Após criar o arquivo HTML precisamos conectar ele com o arquivo Python. Para isso vamos utilizar um *helper* do Flask chamado *render_template*.

```
from flask import Flask, render_template

app = Flask(__name__)

@pp.route('/inicio')
def ola():
  return render template('lista.html')
 
app.run()

```
<div id='pythonnohtml'/>
<h4>Como colocar código Python dentro do HTML:</h4>

O flask tem um diretiva que é a dupla chaves `{{}}`, então usamos essa diretiva para colocar código Python dentro do arquivo HTML.
Dentro dessa diretiva colocamos uma variável e referenciamos essa variável dentro do *render_template* e damos um nome a variável.O *render_template* vai passar o nome da variável para o arquivo HTML e fazer essa comunicação entre os arquivos. 

<div id='fordentrohtml'/>
<h4>Como fazer uma estrutura <i>for</i> dentro do HTML:</h4>

Quando vamos utilizar uma estrutura de repetição precisamos utilizar outra diretiva que não a dupla chaves. E a diretiva que vamos usar para isso é chaves e porcentagem `{%%}` e dentro entre as porcentagens colocamos a estrutura de repetição.

obs: como estamos dentro do HTML precisamos fechar a estrutura de repetição, então no final da estrutura de repetição *for* colocamos `{%endfor%}`.

<div id='classeeobjeto'/>
<h4>Utilizando estrutura de classe e orientação objeto:</h4>

Nesse caso utilizamos estrutura de classe para adicionar mais informações para cada jogo.

<div id='jinja2'/>
<h4>Jinja2:</h4>

Jinja2 é um template escrito em Python que facilita a criação de páginas HTML em aplicações Python. Basicamente, ele serve para permitir que as informações trocadas entre uma plicação escrita em Python e suas páginas HTML seja feita de forma simples e intuitiva.

<div id='acrescentandorota'/>
<h4>Acrescentando mais uma rota:</h4>

Para criar uma nova rota com o objetivo de ser uma nova página na aplicação precisamos criar outro arquivo HTML.

Obs: utilizamos mais uma vez um código pronto disponibilizado pelo curso Alura.

Também é preciso criar uma nova rota no arquivo Python para direcionar para essa nova página.

<div id='metodopostemrequisicaohttp'/>
<h4>Método <i>post</i> em requisição HTTP:</h4>

O protocolo HTTP define um conjunto de métodos de requisição responsáveis por indicar a ação a ser executada para um dado recurso.

Por exemplo, utilizamos o método *get* quando queremos puxar alguma informação do nosso servidor. Já o método *post* utilizamos quando queremos informar alguma coisa para o servidor, passar alguma informação para que ele processe da maneira dele.

Obs: por padrão fica configurado o método *get*.

Ao alterar o método de *get* para post no arquivo HTML ele vai ser apenas um formulário que pega as informações e envia para o servidor. 
Para saber para onde enviar essas informações é preciso especificar no código HTML e no arquivo Python.

<div id='helperrequest'/>
<h4>Helper <i>request</i> dentro de uma rota para capturar as informações do formulário:</h4>

Criamos uma nova rota com o objetivo de receber as informações enviadas pelo formulário através do método post. Essa rota captura as informações com a ajuda do helper *request* do Flask.

Obs: o Flask como padrão coloca que a rota só aceita o método *get*, então devemos informar para ele que também deve aceitar o método *post*.

<div id='debugger'/>
<h4>Debugger:</h4>

O *debugger* facilita as alterações no código.

<div id='helperrequest'/>
<h4>Função <i>return redirect</i>:</h4>

É uma função helper do Flask que redireciona a página.
