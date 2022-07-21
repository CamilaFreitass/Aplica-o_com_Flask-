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
 * [Estilizando a página com CSS e *bootstrap*;](#cssebootstrap)
 * [Como aplicar o estilo na página HTML;](#aplicandoestilo)
 * [Como reutilizar trechos do *template*;](#trechosdotemplate)
 * [Função *url_for*;](#funcaourlfor)
 * [Criando uma tela de *login*;](#teladelogin)
 * [Retendo informações na aplicação;](#retendoinformacoes)
 * [Sinalizando para o usuário;](#sinalizandoparaousuario)
 * [*Secret_key*;](#secretkey)
 * [*Logout*;](#logout)
 * [Melhorando o fluxo de uma rota;](#melhorandoofluxo)
 * [Adicionando boas práticas no código;](#boaspraticas)
 * [O que é CRUD;](#crud)
 * [O que é ORM;](#orm)
 * [Instalando DBMS (banco de dados MySQL);](#instalandodbms)
 * [Criando o banco de dados para a aplicação;](#criandobanco)
 * [Conectando o ORM com a aplicação;](#ormcomaplicacao)
 * [Conectando o ORM com banco de dados;](#ormcombancodedados)
 * [Conexão com as tabelas;](#conexaocomastabelas)
 * [Adequando as rotas ao banco de dados;](#adequandorotas)
 * [Reestruturando o código;](#reestruturandoocodigo)
 * [Completando o CRUD (*Update*);](#completandoocrud1)
 * [Completando o CRUD (*Delete*);](#completandoocrud2)

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

<div id='cssebootstrap'/>
<h4>Estilizando a página com CSS e <i>bootstrap</i>:</h4>

Quando falamos em estilo falamos em CSS e uma maneira de aplicar estilização no site é usando o *framework* chamado *bootstrap* que oferece um arquivo CSS com uma estilização mínima.

<div id='aplicandoestilo'/>
<h4>Como aplicar o estilo na página HTML:</h4>

Acrescentando uma nova tag de link nos arquivos HTML que fará a ligação com o arquivo CSS.

<div id='trechosdotemplate'/>
<h4>Como reutilizar trechos do <i>template</i>:</h4>

Criamos um novo arquivo HTML chamado *template* que é onde vamos colocar todo o código que está duplicado nos arquivos HTML.
O código em *template* é a parte comum que existe em todos os arquivos HTML, no meio (espaço em branco) é onde existe o conteúdo diferenciado.
Com a diretiva `{%%}` indicamos que existe um bloco de conteúdo no meio e também fechamos esse bloco. 
Eliminamos dos arquivos HTML o código duplicado.
Nos arquivos HTML, na primeira linha colocamos a diretiva indicando que esse é o bloco que queremos que seja envolto pelo conteúdo template.html, e na última linha vamos fechar essa diretiva.

<div id='funcaourlfor'/>
<h4>Função <i>url_for</i>:</h4>

É usada para evitar a repetição de ter que alterar URLs em toda a aplicação. Caso não haja a *url_for*, quando houver uma alteração na URL raiz da aplicação será necessário alterar em todas as páginas em que o link estiver presente. 

<div id='teladelogin'/>
<h4>Criando uma tela de <i>login</i>:</h4>

Começamos criando uma nova rota login. Dentro do *render_template* colocamos o nome do arquivo HTML que vamos criar, pois precisamos ter um formulário para colocar as credenciais. 
Também criamos uma rota para autenticar as informações do login e assim direcionar para a página inicial, ou se as informações estiverem incorretas permanecer na página de login.

<div id='retendoinformacoes'/>
<h4>Retendo informações na aplicação:</h4>

No Flask temos um  recurso chamado *session* que guarda as informações por mais de um ciclo de *request*, guardando informações nos *cookies* do navegador.

**Obs:** é preciso configurar um código no arquivo html também.

**Obs:** é necessário uma *secret_key* no servidor para a utilização da *session*.

**Obs:** a *session* **não** é recomendada para a utilização de armazenamento de dados sensíveis. 

<div id='sinalizandoparaousuario'/>
<h4>Sinalizando para o usuário:</h4>

A função *flash* permite colocar uma mensagem rápida e única, mostrando-a para o usuário.
Para mostrar a mensagem é necessário alterar *templates* HTML com a adição de um bloco de código já fornecido pelo documentação do Flask.

<div id='secretkey'/>
<h4><i>Secret_key</i>:</h4>

Como estamos guardando informações no navegador, nos *cookies* do navegador, precisamos adicionar uma camada de criptografia no site.
Essa camada de criptografia garante que o conteúdo não pode ser alterado, contudo, não necessariamente impede a visualização dos dados.

<div id='logout'/>
<h4><i>Logout</i>:</h4>

O que define que fazemos *login* é quando a *session* guarda o nome do usuário, então para fazer *logout* precisamos tirar o nome do usuário da *session*.

<div id='melhorandoofluxo'/>
<h4>Melhorando o fluxo de uma rota:</h4>

Para isso um dos recursos que vamos utilizar é a *query string*, que nada mais é que um modelo clássico de manutenção do estado da página, é um conjunto de valores anexados a URL.

Também utilizamos o *request* para capturar a informação enviada para a *query string*. Além disso, é preciso configurar o arquivo HTML para receber a informação passada, para isso acrescentamos um input e colocamos um atributo do tipo *hidden* que irá guardar as informações que atribuímos a ele.

<div id='boaspraticas'/>
<h4>Adicionando boas práticas ao código:</h4>

Uma das maneiras de melhorar nosso código é utilizando a função *url_for* dentro do *redirect*, e dentro da *url_for* colocamos a função que instância a página desejada. Além disso, também colocamos a *url_for* dentro do arquivo HTML.

<h1>Aprimorando a aplicação com CRUD</h1>

<h3>Agora queremos evoluir um pouco o projeto, de forma que os dados postos no <i>front-end</i> persistem. E para fazermos isso vamos utilizar um banco de dados (MySQL), assim a aplicação será capaz de criar itens diretamente no banco de dados, ler novos itens no banco de dados, alterar itens do banco de dados e deletar itens do banco de dados. Ou seja, vamos fazer CRUD.</h3>

<div id='crud'/>
<h4>O que é CRUD:</h4>

CRUD (Create, Read, Update, Delete) é um sistema que permite fazer a comunicação com o banco de dados de criar, ler, alterar e deletar os itens.

<div id='orm'/>
<h4>O que é ORM:</h4>

O ORM (Object-Relational Mapping) significa mapeamento objeto-relacional, ou seja, é uma técnicaque ajuda na comunicação com o banco de dados. Nesse caso vamos usar o ORM SQL Alchemy. 

<div id='instalandodbms'/>
<h4>Instalando DBMS (banco de dados MySQL):</h4>

Segundo o curso da Alura, para instalar seria necessário apenas digitar o comando abaixo no terminal.

`pip3.exe install mysqlclient`

**Obs:** eu não consegui instalar apenas com esse comando, tive que fazer a instalação por fora.

<div id='criandobanco'/>
<h4>Criando banco de dados para a aplicação:</h4>

O curso da Alura deixou um *script* pronto para criarmos o banco de dados conforme as necessidades da nossa aplicação.

O próxima passo é criar um arquivo Python, nomear de `prepara_banco.py` e colocar o script dentro dele e então esse *script* vai se conectar com o MySQL. Quando instalamos o MySQL ele pede para criarmos um usuário, nesse caso criamos o usuário *root* com a senha *admin*. 
Ainda é preciso instalar a biblioteca MySQL connector que fará a comunicação entre a linguagem Python e o MySQL. No terminal digitamos o seguinte comando:

`pip install mysql-connector-python==8.0.28`

Agora podemos rodar o *script* e pronto, ele já vai criar um banco de dados da Jogoteca.

<div id='ormcomaplicacao'/>
<h4>Conectando o ORM com a aplicação:</h4>

Para conectar o banco de dados com a aplicação utilizamos o ORM (Object-Relational Mapping) e o escolhido foi o SQL Alchemy. O ORM vai pegar os objetos utilizados na aplicação e vai transformar esses objetos em objetos de banco de dados. Para isso ocorrer precisamos fazer duas etapas que são: conectar o ORM com a aplicação e conectar o ORM com o banco de dados.

Então no terminal da aplicação vou digitar o seguinte comando:

`pip install flask-sqlalchemy==2.5.1`

Agora no arquivo jogoteca.py importo o SQL Alchemy:

`from flask sqlalchemy import SQLAlchemy`

Vamos instanciar o objeto de banco de dados que o SQL Alchemy nos dá. Portanto, logo depois da instanciação da nossa aplicação digitamos o seguinte comando:

`vd = SQLAlchemy(app)`

**Obs:** note que dentro como argumento foi passado nossa própria aplicação Flask.


<div id='ormcombancodedados'/>
<h4>Conectando o ORM com o banco de dados:</h4>

Para fazer a conexão com o banco de dados, criamos uma variável e colocamos dentro das configurações da aplicação.

`app.config[‘SQLAlchemy_DATABASE_uri’]`

E passamos um endereço com as configurações do banco de dados e o SQL Alchemy vai entender e fazer a conexão.

```
app.config[‘SQLAlchemy_DATABASE_uri’] = \
‘{SGBD}://{usuario}:{senha}@{servidor}/{database}’.format(
		SGBD = ‘mysql+mysqlconnector’,
		usuario = ‘root’,
		senha = ‘admin’,
		servidor = ‘localhost’,
		database = ‘jogoteca’
	)
```

**Obs:** uma das vantagens do ORM é que caso queiramos mudar o sistema gerenciador do banco de dados, simplesmente mudamos a String e o restante vai permanecer o mesmo.

<div id='conexaocomastabelas'/>
<h4>Conexão com as tabelas:</h4>

Criamos duas classes que serão a conexão com as tabelas.

```
class Jogos(db.Model):
  id = db.Column(db.Integer, primary_key=True, autoincrement=True)
  nome = dbColumn(db.String(50), nullable=False)
  categoria = dbColumn(db.String(40), nullable=False)
  console = dbColumn(db.String(20), nullable=False)
  
  def __repr__(self):
    return'<Name %r>' % self.name
    
class Usuarios(db.Model):
  nickname = dbColumn(db.String(8), primary_key=True)
  nome = dbColumn(db.String(20), nullable=False)
  senha = dbColumn(db.String(100), nullable=False)
  
  def __repr__(self):
    return'<Name %r>' % self.name
```
abaixo de cada classe colocamos uma função de inicialização.
Colocamos a aplicação para rodar mas ainda não está funcionando perfeitamente pois ainda não apagamos as classes que tínhamos criado anteriormente. Contudo mesmo apagando essas classes ainda há problema na aplicação, pois existem rotas que precisam ser alteradas.

<div id='adequandorotas'/>
<h4>Adequando as rotas ao banco de dados:</h4>

Começando com a rota index, percebemos que precisamos de uma lista de jogos. Para isso fazemos uma *query* em cima da tabela de Jogos do banco de dados.

`Jogos.query.order_by(Jogos.id)`

Essa *query* busca a lista de jogos que temos na tabela. E vamos colocar essa lista de jogos dentro de uma variável que vai se chamar lista.

`lista = Jogos.query.order_by(Jogos.id)`

E pronto, essa rota já está de acordo com o banco de dados.

A próxima rota será a autenticar pois ela está pegando um dicionário de usuários que não existe mais. Então vamos fazer uma *query* em cima da tabela de usuários do banco de dados. Quero conferir se existe um usuário com o nickname no banco de dados.

`Usuarios.query.filter_by(nickname=request.form[‘usuario’].first()`

E colocamos essa *query* dentro da variável que vamos chamar de usuário.

`usuário = Usuarios.query.filter_by(nickname=request.form[‘usuario’].first()`

E a rota autenticar vai ficar da seguinte forma:
```
@app.route('/autenticar', methods=['POST',])
def autenticar():
  usuario = Usuarios.query.filter_by(nickname=request.form['usuario']0.first()
  if usuario:
    if request.form['senha'] == usuario.seenha:
      session['usuario logado'] = usuario.nickname
      flash(usuario.nickname + 'logado com sucesso!')
      proxima_pagina = request.form['proxima']
      return redirect (proxima_pagina)
    else:
      flash('Usuário não logado.')
      return redirect (url_for('login'))
```

Agora precisamos alterar a rota criar. Vamos apagar o raciocínio anterior e criar um novo, e a primeira coisa a se fazer é verificar se o jogo que o usuário está tentando adicionar já existe no banco de dados. Então criamos uma variável, colocamos a *query* dentro dessa variável e filtramos. 

`jogo = Jogos.query.filter_by(nome=nome).first`

Então se o jogo já for existente no banco de dados ele vai mostrar uma mensagem. 

```
if jogo:
	flash(‘Jogo já existente!’)
	return redirect(url_for(‘index’))
 ```

Caso não exista o jogo, então podemos incluir ele. Instanciamos um novo jogo da mesma forma que já acontecia na rota criar.

`novo_jogo = Jogos(nome=nome, categoria=categoria, console=console)`

Para incluir esse jogo no banco de dados ele precisa ser instanciado pelo SQL Alchemy.

`db.session.add(novo_jogo)`

E precisamos “comitar” isso:

`db.session.commit()`

E pronto, essa rota está em sintonia com o banco de dados

<div id='reestruturandoocodigo'/>
<h4>Reestruturando o código:</h4>

Como nossa aplicação está dentro de um único arquivo Python e está ficando muito grande, precisamos organizar ela.
Para isso vamos reestruturar o código. 
Então criamos um arquivo chamado `models.py` e colocamos os dois models que criamos anteriormente para fazer a ponte com as tabelas do banco de dados. E apagamos esses models do arquivo `jogoteca.py`. 

O arquivo `models.py` precisa do meu db que é a instanciação do SQL Alchemy, então vamos fazer a importação.

`from jogoteca import db`

Vamos criar também um arquivo python especifico para as rotas chamado `views.py`. Recortamos todas as rotas do arquivo `jogoteca.py` e colamos nesse novo arquivo.
Precisamos fazer algumas importações para o arquivo `views.py`. Voltando no arquivo `jogoteca.py` percebemos que algumas bibliotecas só são utilizadas dentro das rotas.
Portanto, vamos copiar todas essas bibliotecas e colar no arquivo `views.py` e apagar elas do arquivo `jogoteca.py`.

`from flask import render_template, request, redirect, session, flash, url_for`

Também precisamos fazer a importação da nossa aplicação para dentro do arquivo `views.py`.

`from jogoteca import app`

E também precisamos fazer a importação de nossos *models*.

`from models import Jogos, Usuarios`

Agora só precisamos importar o db para o arquivo `views.py`.

`from models import app, db`

Para deixar ainda mais organizado o nosso código, vamos criar um arquivo para deixar as configurações da nossa aplicação.
Esse arquivo vai se chamar `config.py`. Dentro dele vamos colocar a variável da uri que se conecta no banco de dados.
Além disso, a *secret_key* também é uma configuração, então também vamos coloca-la dentro do arquivo `config.py`.

Vamos fazer algumas mudanças. Em vez de `app.secret_key` vamos chamar apenas `SECRET_KEY = 'alura'`.
Vamos criar uma variável universal com o nome `SQLALCHEMY_DATABASE_URI` que vai conter todas as informações.
Voltando em `jogoteca.py` colocamos `app.config.from_pyfile()`, ou seja, a nossa própria aplicação Flask dá a opção de puxarmos as configurações de dentro de um arquivo Python.
Só precisamos passar o nome do arquivo dentro do *from pyfile*.

`app.config.from_pyfile('config.py')`

Precisamos colocar o seguinte código dentro do arquivo `jogoteca.py`.

`if __name__ == '__main__':`

Isso significa que quando rodarmos o arquivo que fez a importação do arquivo `jogoteca.py`, tudo que estiver dentro desse *if* não vai rodar dentro daquele arquivo que está fazendo a importação, só vai rodar quando estivermos rodando o próprio arquivo `jogoteca.py`.

Agora precisamos importar todas as rodas para dentro de `jogoteca.py`.

`from views import *`

Esse asterisco significa tudo, quero fazer a importação de todas as rotas.

Agora com tudo organizado podemos colocar a aplicação para rodar. 


<div id='completandoocrud1'/>
<h4>Completando o CRUD (<i>Update</i>):</h4>

Para poder fazer alterações nos jogos precisamos de algumas coisas:

* Um botão, com o nome "editar", do lado de cada item. Essa botão nos enviaria para uma página de formulário;
* Novo template para a página de formulário onde podemos alterar as informações do item;
* Uma nova rota de "editar";
* Uma nova rota de "atualizar".

A rota "editar" vai ser bem parecida com a rota "novo".

```
@app.route('/editar')
def editar():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login', proxima=url_for('editar')))
    return render_template('editar.html', titulo='Editando Jogo')
```
O template `editar.html` também será parecido com o template `novo.html`. Então copiamos o template de `novo.html` e colocamos no template `editar.html`, e fizemos algumas alterações.
Quando as informações forem alteradas serão enviadas para uma nova rota, que vai se chamar "atualizar".
Então adicionamos essa informação no template `editar.html`.

`<form action="{{ url_for('atualizar') }}" method="post">`

Vamos criar a rota atualizar:

```
@app.route('/atualizar', methods=['POST',])
def atualizar():
    pass
```
Por enquanto ficará assim.

Agora vamos criar o botão "editar". No template `lista.html` criamos uma nova coluna com a tag.

`<td><a> href="{{ url_for('editar') }}"<Editar</a></td>`

E pronto!

Quando vamos editar um jogo precisamos que as informações daquele jogo apareçam.
Além disso precisamos ter uma distinção de formulário entre os jogos. 
então vamos tentar persistir as informações pelas camadas que temos da aplicação.
No template `lista.html` dentro da `url_for` colocamos uma variável como id e passo o id do jogo específico. 

`<td><a href="{{ url_for('editar', id=jogo.id) }}">Editar</a></td>`

Agora vamos editar a rota "editar" para ela capturar as informações do id.
Contudo, só passar o id não é suficiente, precisamos fazer uma `query`dentro do banco de dados para trazer o objeto jogo para passar as informações para o template `editar.html`.
E a rota "editar" ficou assim:

```
@app.route('/editar/<int:id>')
def editar(id):
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login', proxima=url_for('editar', id=id)))
    jogo = Jogos.query.filter_by(id=id).first()
    return render_template('editar.html', titulo='Editando Jogo', jogo=jogo)
```
Agora no `editar.html` nos campos de inputs vamos adicionar os seguintes valores:

`value="{{ jogo.nome }}"`

`value="{{ jogo.categoria }}"`

`value="{{ jogo.console }}"`

Agora quando clicarmos em um jogo, ele já vai vir com as informações!

Precisamos acabar a rota "atualizar". Como a rota "atualizar" está recebendo as informações do formulário de `editar.html`, vamos passar as informações do id através desse formulário.
Dentro de `editar.html` criamos um novo input.

`<input type="hidden" name="id" value="{{ jogo.id }}">`

E a rota "atualizar" ficou da seguinte forma:

```
@app.route('/atualizar', methods=['POST',])
def atualizar():
    jogo = Jogos.query.filter_by(id=request.form['id']).first()
    jogo.nome = request.form['nome']
    jogo.categoria = request.form['categoria']
    jogo.console = request.form['console']

    db.session.add(jogo)
    db.session.commit()

    return redirect( url_for('index'))
```

Agora podemos fazer as alterações.

<div id='completandoocrud2'/>
<h4>Completando o CRUD (<i>Delete</i>):</h4>

Vamos criar o botão "deletar". Lá na `lista.html` onde criamos o botão "editar" e vamos criar do lado dele o botão "deletar".

`<a href="{{ url_for('deletar', id=jogo.id) }}">Deletar</a>`

Também precisamos criar uma rota para deletar.

```
@app.route('/deletar/<int:id>')
def deletar(id):
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login'))

    Jogos.query.filter_by(id=id).delete()
    db.session.commit()
    flash('Jogo deletado com sucesso!')
    return redirect(url_for('index'))
```
Pronto, mais uma etapa concluida com sucesso!

<div id='implementandoimagens'/>
<h4>Implementando imagens:</h4>

Queremos que cada novo jogo adicionado poça relacionar uma imagem, então vamos implementar isso.
Precisamos adicionar um novo botão na rota `/novo`, ou seja, estamos falanco do formulário então é preciso alterar o template `novo.html`.
Vamos adicionar um novo *input*:

`<input type="file" name="arquivo" accept="jpg">`

Colocamos o tipo de *input* que vai ser *file*, o nome que é importante para depois associar a informação na rota, e além disso também informamos o tipo de arquivo que ele vai aceitar.
Queremos que ele aceite apenas arquivos do tipo `.jpg` que é um tipo de arquivo de imagem.

Agora vamos ajustar essas informações na rota `/criar`.

```
arquivo = request.files['arquivo']
arquivo.save(f'uploads/{arquivo.filename}')
```

Criamos uma variável com o nome `arquivo` e dentro dessa variável vamos receber as informações da imagem que serão passadas no formulário.
Para receber as informações de um formulário uso o *request*, porém não será o *request.forms* pois não estamos trabalhando com informações simples, estamos recebendo informações de um arquivo. 
Então usamos o *request.files* e dentro desse request colocamos o nome do arquivo que colocamos lá na tag de *input* que no caso vai ser `arquivo`.
Para guardar essas informações que recebi na variável arquivo criamos uma pasta dentro da aplicação chamada "uploads".
Então logo depois que eu receber as informações do formulário a respeito da imagem e declarar essa variável arquivo, na linha seguinte vou colocar, `arquivo.save`.
Esse comando vai salvar as informações dessa variável arquivo no caminho que direcionar ele dentro do ".save".

Ainda é preciso adicionar o *enctype* lá no formulário. O *enctype* é o tipo de arquivo que quero adicionar. Lá em `novo.html` na tag de formulário tem *form*, tem *action* que vai estar passando as informações para a rota criar e o método *post*. Então do lado colocamos o *enctype*. Isso vai permitir que mandemos realmente arquivos para o nosso servidor.

`enctype="multipart/form-data"`

Para gantir que vamos ter arquivos únicos para cada jogo que cadastrarmos, vamos alterar o caminho no `arquivo.save`.

`arquivo.save(f'uploads/capa{novo_jogo.id}.jpg')`

Trocamos `arquivo.filename` por `novo_jogo.id` e logo depois colocamos `.jpg` para indicar que é uma imagem. 
Para não deixar só o `id` vamos colocar a capa antes da chave.

Também vamos melhorar a forma de encontrar o diretório *uploads*. 
Dentro de `config.py` vamos criar uma variável `UPLOAD_PATH` e colocar dentro algum caminho relativo.

`UPLOAD_PATH = os.path.abspath(__file__)`

O *dunder file* `__file__` é uma forma de referenciar o próprio arquivo que estamos. 
E para achar o caminho absoluto que este arquivo está utilizamos a biblioteca OS Operating System.

Só que ainda precisamos captar o cominho absoluto desde o início e não só desde "jogoteca". 
Assim, podemos usar a função do OS `ps.path.dirname()` e colocamos tudo dentro dessa função.

```
UPLOAD_PATH = os.path.dirname(os.path.abspath(__file__)) + '/uploads'
```

E para achar o caminho "uploads" basta fazermos uma concatenação de String `+ '/uploads'`.

Em `views.py` na rota `/criar` vamos adicionar a variável `upload_path` e dentro dela colocamos a informação da aplicação.

`upload_path = app.config['UPLOAD_PATH']`

E no `arquivo.save`:

`arquivo.save(f'{upload_path}/capa{novo_jogo.id}.jpg')'`

Pronto. Agora temos um caminho melhor para colocarmos as imagens.

Agora vamos mudar a interface do formulário de "Novo Jogo" adicionando uma imagem de capa padrão.

Em `novo.html` , logo depois da tag form, criamos uma estrutura de tags que vai comportar a imagem. 
```
 <figure class="imag-thumbnail col-md-4">
          <img class="img-fluid" src="{{ url_for('imagem', nome_arquivo='capa_padrao.jpg') }}">
          <figcaption>
            <label class="fileContainer">
              Mudar Capa
              <input type="file" name="arquivo" accept=".jpg"
            </label>
          </figcaption>
        </figure>
```

Vamos em `views.py` e criamos uma nova rota. 

```
@app.route('/uploads/<nome_arquivo>')
def imagem(nome_arquivo):
    return send_from_directory('uploads', nome_arquivo)
```

Agora vamos melhorar um pouco o estilo. Vamos criar um novo arquivo CSS chamado `app.css`.

Obs: o código desse arquivo já foi disponibilizado pré-pronto.

Em `template.html` habilitamos na aplicação o arquivo CSS.

```commandline
<link rel="stylesheet" href="{{ url_for('static', filename='app.css') }}">
```
Ainda precisamos ir no template `novo.html` e colocar as devidas classes que temos em cada uma das nossas tags.

`<figure class="img-thumbnail col-md-4">`

`<img class="img-fluid">`

`label class="fileContainer"`

Nossa página já está melhor!

