# Criação de um site em HTML estático

De forma prática

Partindo do site criado no tutorial citado ao final (gratidão aos autores)

Este site destina-se a listar por categorias, todos os meus repositórios, inclusive os forks no Github. Como hoje, 08/11/2022, existem 909 repositórios na minha conta, sendo 130 meus e os demais forks, fica muito trabalhoso percorrer ou pesquisar por repositórios. Então resolvi criar um repositório com o nome index e listar todos os repositórios agrupados por categorias. Então, durante a elaboração resolvi criar uma Github page para o mesmo. Procurei um tutorial sobre a criação de um site com Bootstrap, pois para mim é a solução mais prática. Então encontrei o tutorial do link acima, que contém os arquivos para download. Este me agradou especialmente por dois motivos, por ser relativamente simples (seu CSS/BS) e especialmente por ser responsivo.

## Projeto do site

### Categorias

Front-end Back-end Mobile DevOps Servidores Nocode Cursos Ferramentas Extra

Deixarei todos os arquivos no raiz para facilitar meu trabalho.

## Metodologia

A forma mais prática que encontrei para a construção foi usando o método load() do jQuery. Assim fica similar ao include do PHP, não repito código e reduzo meu trabalho.

Criarei uma pasta includes e dentro dela:
- header.txt - contendo o head, os links e o menu, até a tag </nav>
- footer.txt, da tag <footer> pra baixo

O texto que ficará no body estará dentro das tags <header> e </header>

Troquei os arquivos dos assets pelos respectivos CDN, para facilitar apra mim, exceto main.css e main.js.

Durante a construção tive que realizar vários ajustes no template original para adaptar ao meu conteúdo, mas sempre tendo o cuidado de manter o mesmo responsivo.

O uso do método load precisa ser no diretório web, pois se for executado fora dele, não funciona e receberemos erro no console:

"Requisição cross-origin bloqueada: A diretiva Same Origin (mesma origem) não permite a leitura do recurso remoto em file:///backup/transp/index/includes/header.txt (motivo: requisição CORS não é http)."

## Conteúdo

A forma mais produtiva de criação de sites que já experimentei é usando o CMS Joomla. Quando vou criar um site em HTML estático ficoc procurando formas de fazer isso mais produtivo, pois relativamente é algo trabalhoso.

- Inicialmente criei uma lista em arquivo texto, por categoria, dos repositórios
- Seleciono cada grupo, copio e colo num arquivo em branco do LibreOffice Texto. Caso tenha hífens eu os removo todos com Ctrl+H
- Porque o LibreOffice? Porque com ele crio links de forma prática. Basta colocar o cursos ao final do texto e teclar espaço. Então ele cria o link
- Quando transformo todos em link, teclo Ctrl+A, Ctrl+X e vou ao editor HTML SunEditor e teclo Ctrl+V para colar os links na textarea.
- Depois de organizar um pouco eu clico no botão para exibir código  fonte
- Então seleciono tudo e teclo Ctrl+X
- Agora eu crio o arquivo que será o body do arquivo do site. Um exemplo: css.txt (depois o mudarei para .html). Abro o css.txt e colo o conteúdo do editor.

Este site tem como conteúdo basicamente links. No caso de conteúdo comum, com texto formatado, imagens, vídeos, etc, eu geralmente também uso o editor SunEditor para criar com conforto e exporto o código fonte.

## Como crio cada arquivo

Exemplo, para criar o arquivo css.html, eu procedo assim:

<meta charset="utf-8">
<div id="header"></div>
<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
<script>$( "#header" ).load( "includes/header.txt" );</script>

		<header class="main">
			<div class="body text-center">
				<h1>CSS</h1>
			</div>
			<div class="container p">

Aqui fica a relação de links de repositórios sobre CSS

			</div>
        </header>

<div id="footer"></div>
<script>$( "#footer" ).load( "includes/footer.txt" );</script>


## Crédito pelo original

https://websitesetup.org/bootstrap-tutorial-for-beginners/

## Referências

https://www.umov.me/tecnologia-no-code

https://awari.com.br/linguagens-de-programacao-front-end/

https://harve.com.br/blog/desenvolvimento-web/o-que-e-backend-guia-completo/

https://www.totvs.com/blog/developers/metodologia-devops/
