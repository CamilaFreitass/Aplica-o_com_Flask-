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
