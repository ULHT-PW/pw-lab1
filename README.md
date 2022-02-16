**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

# Programação Web - Laboratório 1: <br>*Conhecer a Internet com a minha primeira página Web*

**OBJECTIVO**: Nesta ficha:
* criará uma primeira página na Web. 
* Irá conhecer e analisar vários aspectos ligados com a Internet e o protocolo HTTP
* Criará uma segunda páagina onde reportará tudo o que observou.
* O seu website ficará online num servidor na nuvem, numa conta criada por si!
  
**PRÉ-REQUISITOS**: Instale o PyCharm, IDE que utilizaremos nesta disciplina, para editar o código HTML de forma fácil. Senão, pode sempre usar o Notepad++.

# 1. Alojamento de página Web na cloud

## Criação de uma página Web
* Crie uma pasta lab1. 
* Abra a pasta com o PyCharm
* Dentro dessa pasta, crie o ficheiro `index.html` com o seguinte código fonte HTML; 

![image](https://user-images.githubusercontent.com/42048382/154178599-55386ae4-f531-4b77-a50f-c583090e5696.png)


O HTML é uma linguagem de marcação para construir páginas Web. OS ficheiros HTML possuem marcadores (*tags*), palavras entre parênteses angulares (`<` e `>`) que são comandos de formação da linguagem. 

No elemento `<title>Primeira página</title>`:
* `<title>` é o marcador de abertura
* `</title>` é o marcador de fecho
* `Primeira página` será o conteúdo afetado pelo marcador <title>, que neste caso especificará o título da barra de navegação.

No ficheiro em cima poderá ver a utilização de vários marcadores:
* `h1` = marcador que define um titulo - heading1 (`h2` um subtítulo, `h3` um subsubtítulo, ...)
* `p` = marcador que define um parágrafo
* `ul` = marcador que define uma lista não numerada (`ol` para lista numerada)
* `li` = marcador que define uma linha
* `img` = marcador que define uma imagem
* `a` = marcador de âncora para hiperlink, especificado como valor do atributo `href` 

Dentro de um marcador podem ser especificados pares de atributo = valor. Os atributos modificam os resultados padrões dos elementos e os valores caracterizam essa mudança. Existem neste ficheiro os seguintes atributos:
* `src` = atributo que define o nome do ficheiro com a imagem
* `href`= atributo que define o URL da hiperligação
Nas próximas aulas falaremos mais em detalhe destes aspectos.

Crie, na pasta `lab1`, a pasta `images`, e guarde dentro desta a imagem  `wordcloud.png` em baixo.

![](wordcloud.png)

Uma vez editado, abra o ficheiro `index.html` com um Browser para ver se visualiza corretamente a imagem em baixo.
![](index-renderizado.png)

## Criacao de repositorio GitHub
* Crie, na sua conta GitHub, o repositório `pw-lab1`
* Caso não tenha, descarregue de www.git-scm.com o git e instale-oadd.
* abra uma janela de comandos (pode usar o Terminar do Pycharm) e defina a sua identidade para o git, caso não o tenha feito em LP2:
```bash
> git config --global user.name "username_usado_no_git"
> git config --global user.email "iniciais@meuemail.pt"
```
* Na pasta lab1 execue os seguintes comandos (# indica início de um comentário, que não deverá escrever):
```bash
> git init  # cria repositório git
> git add *   #indica ao git para rastrear todos os ficheiros
> git commit -m "Primeira pagina"   # guarda mudanças no git
> git branch –M main
> git remote add origin https://github.com/<username>/pw-lab1 # Adiciona o endereco do repo do git
> git push -u origin main # carrega e atualiza repo do GitHub
```
Verifique que os dados estão noGitHub.
  
  
## Alojamento da sua página na Cloud
Crie uma conta no [Heroku}(https://www.heroku.com/), plataforma para alojamento de aplicações na cloud. 
De forma a que o alojamento na cloud funcione com sucesso deve seguir os seguintes passos:
* Crie dois ficheiros novos na pasta pw-lab1:
* * `index.php` Com o seguinte conteúdo: `<?php include_once("index.html")  ?>`
* * `composer.json` com o seguinte conteúdo: `{}`
* Sincronize o git e Github com as alterações, com os seguintes comandos:
```bash
> git add *   #indica ao git para rastrear todos os ficheiros, incluindo os novos
> git commit -m "incluidos ficheiros para Heroku"
> git push -u origin main
```
  
* Crie uma conta no Heroku, https://signup.heroku.com/login 
* Duas opções para alojar a sua página no Heroku:
* usando CLI:
  * instale o [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli#install-with-an-installer) (Command Line Interface)
  * execute os seguintes comandos:
  
```bash
  heroku login
  heroku create -a <seuNumero>-pw-lab1
  git push heroku main  
```
  
  * conecte o Heroku com o GitHub:
     * Na conta Heroku, crie uma aplicação, atribuindo-lhe como nome o seu <seuNumero>-pw-lab1
     * Entrar nas definições da aplicação criada, e clicar na tab `Deploy`
     * Na secção de `Deployment Method` conectar a aplicação com o Github
     * Navegando até ao fim da página, até à secção `Manual deploy`, devem escolher o branch indicado do repositório e clicar em `Deploy branch`
     * Um vez realizado com sucesso, clicar no botão `Open app` no topo da página, e visualizar a página HTML 




# 2. Conhecer a Internet

Vamos explorar alguns aspectos da Internet, a rede de routers e cabos que suportam Web. Deverá anotar e guardar um conjunto de imagens de todos os passos que são indicados em baixo, que serão usados no final para criar uma nova página HTML.

## Endereços IP
1. Obtenha informação sobre o IP do seu PC e seu telemóvel.
    * obtenha e anote o endereço IP do seu computador. Pode obter isso de várias formas. A mais simples é perguntar no Google "what is my ip". Anote onde está localizado, usando por exemplo a ferramenta https://whatismyipaddress.com/ip-lookup. Observe o mapa, fazendo zoom o máximo que conseguir para verificar o grau de exatidão. guarde uma imagem do mapa que localiza (faça Tecla Windows+Shift+S para usar a Snipping Tool).
    * Obtenha e anote a mesma informação do seu telemóvel, se tiver dados móveis.
1. Obtenha informação sobre o IP do servidor Heroku onde está a sua app.
    * Obtenha e anote o endereço IP do servidor Web onde está alojada a sua página no Heroku
    * anote onde este está localizado, usando a ferramenta https://whatismyipaddress.com/ip-lookup.  Guarde uma imagem do mapa que a localiza.

## Percurso
Traceroute (comando tracert) é uma ferramenta de diagnóstico que rastreia a rota que os pacotes IP fazem, desde o seu computador até um endereço IP destino/ou URL que especifique. Este identifica os routers pelos quais os pacotes passam até o seu destino, indicando o tempo que demoram por "salto" entre router. 

1. A forma mais clássica é através da linha de comando e escreva tracert e especifique o endereço IP obtido anteriormente:
``> tracert <endereço IP ou URL sua app>``. guarde esta informação.
1. Use a ferramenta GeoTraceroute, Em https://geotraceroute.com/, para visualizar graficamente por onde passam os pacotes IP, até chegar ao seu servidor Heroku. Escolha como origem (source) Portugal, e como destino o URL do seu site. Registe os saltos, indicando o país, e distância de cada salto. Quando fizer a página, pode procurar na Internet e inserir uma pequena image da bandeira do país. Com a ferramenta de Snip (Tecla Windows + Shift + S) copie a imagem do globo que cubra os saltos dados, e guarde-a como um ficheiro jpg ou png, para inserir também na página report.html.

# 3. Acesso via HTTP à minha página Web

## HTTP

O protocolo de troca de mensagens entre um cliente e um servidor Web é o HTTP. Um Web browser (Chrome, Safari, Firefox, etc) é uma aplicação que corre numa máquina "cliente" (o seu portátil por exemplo) e é capaz de enviar um pedido usando o protocolo HTTP a um servidor Web:
* O cliente pode pedir uma determinada página Web através de uma mensagem HTTP GET. O servidor Web irá responder-lhe a esse pedido, enviando os conteúdos correspondentes. Tipicamente é recebido um ficheiro HTML juntamente com algumas imagens e outros ficheiros auxiliares, sendo o browser capaz de representar visualmente o conteúdo. 
* O cliente pode também enviar ao servidor Web dados que preencheu por exemplo num formulário, através de uma mensagem HTTP POST. 
Esta é a arquitetura cliente-servidor. 

No seu browser, insira o URL da sua página Heroku. Nesse instante será feito enviado ao servidor Web um pedido (a mensagem chama-se mensagem HTTP GET) do conteúdo correspondente a esse URL, que lhe será enviado pelo servidor em modo de resposta. Visualise o código recebido, clicando com o botão direito do rato e selecionando "ver código fonte" (view page source) ou simplesmente premindo Ctrl + U. Verifique o que aparece: é o que escreveu!

## Inspect

Todos os browsers têm uma ferramenta (*browser developer tool*) que permite inspeccionar ficheiros descarregados pelo browser, permitindo analisar uma grande variedade de informação.
USe por exemplo o Chrome para abrir a sua página, e clicando no botão direito do rato, selecione *Inspect*, ou selecione Ctrl+Shift+i.

Selecione a barra network. Clique na janela  do seu browser onde está o URL do seu site e faça novamente Enter: 
* Explique o que aparece. Com a ferramenta de Snip (Tecla Windows + Shift + S) copie a imagem com info dos ficheiros descarregados. 
* Anote quantos ficheiros são descarregados na sequencia de um clique num hiperlink.
* Anote o tipo de ficheiros, timings de espera e de descarga.
* Selecione cada um dos ficheiros descarregados. Anote o que observa, quando seleciona:
   * preview
   * Headers
   * Timing

Faça o mesmo agora para o site da lusófona, mas aqui observando apenas (sem necessidade de anotar, pois a quantidade de informação é muito maior :-)).

# 4. Página Web `report.html`

Com base em todas estas observações crie uma nova página HTML, `report.html`, onde reporte tudo o que observou. Seja criativo e divirta-se! Crie secções semelhantes às anteriores, inclua a informação/imagens obtidas e faça uma análise crítica do que observa.
  
Para fazer a nova página:
* Deverá ter uma estrutura base semelhante a `index.html`, alterando o ceontúdo do `body` e do `title`.
* Utilize etiquetas para estruturar o seu conteúdo, etiquetas de heading (h1, h2, h3, ....), assim como para listar (ul) e enumerar (ol) (pesquise na internet, nna W3Schools, por exemplo https://www.w3schools.com/tags/tag_ul.asp).
* Dentro do body, comece com um titulo `<h1>A Internet e a Web</h1>`
* por baixo do titulo da pagina report.html e da index.html insira um menu, palavras com hiperlinks para cada uma das páginas:
```html
    <p><a href="index.html">Programação Web</a>  <a href="report.html">A Internet e a Web</a></p>
```
* Guarde as imagens recolhidas na pasta `images`. 
* Abra num browser a pagina report.html e verifique que está tudo bem, e que os links do menu funcionam.
* A estrutura das pastas deverá ser como em baixo (com mais imagens na pasta img):
```
projeto
+-- lab1
|   +-- index.html
|   +-- report.html
|   +-- index.php
|   +-- composer.json  
|   +-- images
    |   +-- wordcloud.png
    |   +-- ...
```

* Guarde as alterações no git, faça upload para o seu repositório no GitHub, e sincronize com o Heroku: 
```
> git add *   
> git commit -m "criei a pagina report.html"
> git push -u origin main
> git push heroku main  
```  
* Verifique que ambas as páginas estão operacionais no Heroku.


# 5. Submissão do Laboratório
* Submeta neste [link](https://forms.gle/yTsVwecqnvaTNtWKA) o seu laboratório.
* Deverá fazer esta tarefa antes da sua próxima aula prática, onde este será avaliado. 

# Fim
Parabéns por ter chegado ao fim! Esperamos que tenha gostado de conhecer um pouco do funcionamento da Internet e de ter feito a sua primeira página Web &#127760;!
