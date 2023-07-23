#### 22/07/2023

Curso de iOS: auto layout com Constraints

@01-Criando um novo projeto

@@01
Apresentação

[00:00] Olá, boas-vindas à Alura! Esse é o curso de criação de layouts para iOS utilizando o framework UIkit.
[00:08] Nesse curso nós vamos trabalhar com um projeto novo e remodelado, o Alura Viagens. É o projeto que nós vamos implementar na prática para estudarmos o assunto principal do curso, que é uma das técnicas de auto layout que nós temos no iOS, chamada constraints.

[00:25] A ideia principal é estudarmos como criar um layout e o adaptamos para ser responsivo em outros dispositivos como, por exemplo, o iPad.

[00:38] Nós vamos começar o curso desde o início, revisando alguns componentes essenciais de UI que nós temos aqui, como labels, view e imagens; como fazemos para arredondar view e alterarmos a customização de textos.

[00:54] Também vamos aprender a trabalhar com células customizadas na nossa TableView, como essa de viagem que você está vendo aqui.

[01:00] Ao decorrer do curso, nós vamos estudando várias das técnicas que nós temos de constraints, até que cheguemos nesse resultado para iPhone e também iPad.

[01:12] Para concluir esse curso sem nenhum problema, é interessante que você já tenha feito os cursos iniciais de Swift aqui na plataforma da Alura — são os cursos de Swift parte 1, 2 e 3; onde nós falamos do fundamento da linguagem e da parte do foundation — ou que você tenha conhecimentos equivalentes sobre a linguagem.

[01:31] Esse é o conteúdo que nós vamos ver durante esse curso, e eu espero você!

@@02
Criando um novo projeto

[00:00] Olá, boas-vindas à Alura! Eu sou o Ândriu e eu serei o seu instrutor durante esse curso, onde nós vamos falar de criação de layout para iOS, utilizando o framework UIkit.
[00:12] Para começar, eu vou te apresentar qual projeto nós vamos utilizar como base para desenvolvimento. Nós temos aqui o projeto Alura Viagens remodelado, é um novo projeto.

[00:26] E é esse projeto que nós vamos trabalhar e desenvolver durante esse curso!

[00:34] O que começaremos a atacar nesse projeto? Uma dica é sempre entender quais são os componentes que temos antes de começarmos a colocar a mão na massa.

[00:47] Quando eu digo componentes, não é saber o nome de cada componente tecnicamente. Eu tenho aqui um UI “Label”, uma UI “Image View”, uma UI “Table View”, não é nada de nomes técnicos.

[01:01] Mas sim, você olhar a estrutura do layout e começar a entender de que forma foi feita. Nós temos aqui, por exemplo, uma listagem onde eu tenho um elemento abaixo de outro com scroll.

[01:16] Nesse caso, são viagens, uma viagem embaixo da outra. Nós temos aqui o cabeçalho onde mostra o nome do aplicativo, nós também temos dentro do cabeçalho um banner e a lista.

[01:34] Esse já é um bom ponto de partida para começarmos a entender como funciona a criação com UIkit. Nós temos o cabeçalho, que você var ver bastante com o nome de header. Nós temos também a lista de viagens.

[01:52] Basicamente, nós temos duas divisões importantes nesse layout. Começaremos criando um novo projeto. Eu tenho o Xcode instalado - caso você ainda não tenha o Xcode instalado, basta você ir na Apple Store, procurar por Xcode e fazer o download.

[02:14] Com o Xcode aberto, eu vou clicar em criar um novo projeto, ou seja, "Create a new Xcode project"... Cliquei nessa opção e ele vai abriu uma caixa com algumas informações.

[02:27] É importante você verificar se já está marcada a opção “iOS” nessa parte superior. Se a opção “App” também já está marcada.

[02:37] Nós vamos utilizar essas opções. Vou clicar em "Next" e terei algumas configurações do projeto -como o nome, vou colocar “AluraViagens”.

[02:51] Aqui também é importante que você verifique se já está marcada a opção “Storyboard”, nós temos as opções “SwiftUI” e “Stoyboard”. Nesse caso, utilizaremos o “Storyboard”. Também verifique se a linguagem também é a linguagem Swift.

[03:05] Agora eu vou clicar aqui em próximo, "Next" e vou salvar o meu projeto na área de trabalho. Cliquei em "Create".

[03:17] Quando criamos o projeto, ele já nos traz alguns arquivos prontos. Nós temos aqui o “AppDelegate.swift”, o “SceneDelegate.swift”, um arquivo chamado “ViewController.swift”, um arquivo chamado “Main.storyboard”, os “Assets”, “LaunchScreen.storyboard” e “Info.plist”.

[03:35] Quando falamos em construção de layout, basicamente temos três técnicas para fazermos essa construção. A primeira é utilizando o storyboard, "Main.storyboard".

[03:45] Que é essa forma onde vemos as telas que vamos criar e elas se conectam dentro de um arquivo ou vários storyboards. Nós temos a criação de XIB, que é também utilizando a interface builder, ou seja, toda essa facilidade de você ver o layout e utilizar a library para conseguir colocar alimentos, label, botões e tudo mais.

[04:14] Basicamente, arrastando eles para dentro. Nós temos também a forma através de código, chamada View Code - que é você digitando código e ele gera o layout.

[04:27] Nós vamos utilizar o storyboard, que é essa que já está aberta. Como você pode perceber, ele simula uma tela de um iPhone - que é exatamente o que nós queremos.

[04:40] Temos uma tela de um iPhone e tudo que colocarmos aqui dentro vai ser exibido para o usuário. É uma view onde colocamos o que quisermos. Eu tenho aqui o simulador. Clicando em “Simulator", eu tenho aqui o projeto. Nós começaremos criando uma lista simples.

[05:00] Repare que temos uma lista bonita, com várias informações, imagens, nomes, descrições, valores e outras informações; mas para começarmos, criaremos uma lista simples.

[05:17] Eu vou abrir o componente chamado “Library” no canto direito superior, que é a nossa biblioteca, "Library". Essa opção aqui, o sinal de adição (“+”).

[05:27] Eu vou clicar nessa opção e ele vai abrir uma caixa com várias opções, com vários elementos para que consigamos desenvolver o nosso projeto. Nós temos “Label”, botão, um componente chamado “Segmented Control”, “Text Field”, “Slider”, “Swicth”, “Actovoty Indicator View”, entre outros.

[05:47] O que precisamos entender aqui? Que existem vários componentes e aos poucos nós vamos utilizando vários dos principais que você vai encontrar no mercado, ou quando você for desenvolver o seu projeto pessoal. Passaremos pelos principais que, com certeza, você vai utilizar.

[06:06] Como eu acabei de falar, nós temos aqui uma lista. Qual é o componente que podemos utilizar para criarmos essa tabela? Nós temos aqui um componente chamado “Table View”, é um componente onde conseguimos listar informações e é exatamente isso que precisamos nesse momento.

[06:27] Eu cliquei em cima de "Table View". Eu vou clicar e arrastar para dentro da nossa tela. Nós temos aqui uma tela.

[06:35] Repare que é comum você ouvir as pessoas chamarem de “View Controller”, por causa dessa nomenclatura que nós temos aqui, um controlador de view.

[06:48] Para cada tela - que é essa que estamos vendo, a tela do celular - nós temos que ter um arquivo para controlarmos essa tela. Esse arquivo se chama “View Controller”, mas poderia se chamar qualquer outro nome.

[07:03] Eu coloquei uma tabela, uma “Table View”. Vou clicar e redimensionar ela para que ocupe todo o espaço. Já coloquei a minha tabela dentro do nosso “ViewController” e agora nós vamos aprender a utilizar uma “Table View”.

[07:24] Nós temos a parte da view, que é o que estamos vendo aqui e nós temos a parte da configuração dessa view, que é no arquivo "View Controller".

[07:36] O que vamos fazer? Temos que entender como funciona uma “Table View”. Se você parar para pensar, provavelmente você já utilizou Word ou algum arquivo de documentos do Google ou da Microsoft para edição de texto.

[07:55] Em algum momento provavelmente você já precisou criar algumas tabelas - // Tabelas. Quando você cria uma tabela no Word, por exemplo, ele te dá a opção de colocar o número de linhas, em uma tabela do Word você pode colocar o número de linhas, // numero de linhas.

[08:15] E o número de colunas. Também você pode configurar cada linha. O que é configurar cada linha? Por exemplo: eu quero fazer uma lista das coisas que eu preciso comprar no mercado, eu preciso comprar 10 itens, então eu coloco o número de linhas: = 10.

[08:36] E eu também vou colocar em cada linha as coisas que eu preciso comprar. Eu vou colocar, por exemplo, o pão na primeira linha, na segunda linha eu preciso comprar também ovos, na terceira linha eu vou colocar que eu preciso comprar leite e assim por diante - // 1 linha = pão, // 2 linha = ovos e // 3 linha = leite.

[09:02] Essa é uma tabela básica que criamos no Word, aqui é a mesma coisa. Vamos fazer essa abstração, como criamos uma tabela no nosso aplicativo. Basicamente, precisamos das mesmas informações: o número de linhas e o que cada linha vai ter, só que agora aprenderemos a fazer isso utilizando a linguagem Swift.

[09:25] Quando trabalhamos com o “Table View” é comum utilizarmos um recurso que a linguagem nos fornece chamado de protocolos. Se pararmos para pensar, o que é um protocolo? Por exemplo: quando você vai a algum lugar e está escrito "respeite os protocolos de segurança", provavelmente você tem que colocar um capacete ou óculos para você não se machucar.

[09:50] Ou você vai em um hospital e está escrito "respeite os protocolos" - um médico, por exemplo, coloca o avental e tudo mais. O que eu quero dizer com isso? Protocolos são algumas regras que temos que seguir para que consigamos fazer alguma coisa.

[10:07] Aqui é a mesma coisa, nós precisamos, obviamente, implementar um protocolo para a “Table View” funcionar. Como eu implemento esse protocolo? Eu posso vir na linha 10, colocar uma vírgula (,) e o nome do protocolo, que é , UITableViewDataSource.

[10:27] O que eu acabei de fazer? Eu disse que o meu View Controller vai implementar o protocolo chamar UITableViewDataSource. Só que ele já está reclamando aqui que não estamos seguindo esse protocolo.

[10:42] Para seguirmos esse protocolo, precisamos basicamente de dois métodos: um onde vamos dizer quais são as linhas, qual a quantidade de linhas; e o outro, como vai ser cada linha.

[10:57] Se eu clicar no símbolo vermelho de erro e clicar em “Fix”, ele já vai me trazer dois métodos. Deixe-me passar tudo isso para a linha debaixo, só para ficar com uma visualização melhor.

[11:14] Vamos tentar ler esse método e ver o que entendemos. O tableView ele fala que estamos utilizando a tableView e dá isso na assinatura do método.

[11:25] Aqui, que é a parte mais importante, o número de linhas na sessão, numberOfRowsInSection. Número de linhas, lembra que eu falei que precisamos falar qual o número de linhas? E embaixo nós temos também o método cellForRowAt.

[11:42] Ou seja, célula para linha - qual vai ser a célula para a linha 1, qual vai ser a célula para a linha 2, qual vai ser a célula para a linha 3 e assim por diante. Que é exatamente a parte onde preenchemos cada linha

[11:59] Para começarmos a fazer o nosso projeto rodar com o nome de algumas viagens, por exemplo, ele pede que retornemos um Int, um inteiro. Vou retornar, por exemplo, 10, vou deixar fixo, que é só para começarmos a entender como funciona - return 10.

[12:20] E na linha debaixo nós precisamos de uma célula, ou seja, ele pede no retorno que implementemos um UITableViewCell. O que eu vou fazer? Eu vou criar uma célula e inicializar ela passando um estilo default: let cell = UITableViewCell(style: .default,.

[12:49] Esse reuseIdentifier: String?) por enquanto não vamos utilizar, eu não vou passar nada. Eu vou colocar aqui cell.textLabel?, que é basicamente uma informação que eu vou colocar na célula; e eu vou setar um texto para isso, .text = "viagem.

[13:13] O número de linha que eu coloquei aqui - por exemplo: 10 - ele vai colocar viagem 1, viagem 2, viagem 3 até chegar na viagem 10. Na verdade, a indexação é de 0 a 9, vai colocar de 0 a 9.

[13:27] Eu vou colocar aqui o número de linha que ele está passando, que é o /(indexPath.row), ou seja, a linha. Eu vou retornar isso para o método, vou dar um return e vou retornar a célula: return cell.

[13:44] Você tem o título, para Label que nós temos aqui na célula e em seguida o número de linhas que ele está passando no momento. Vamos tentar rodar o projeto para vermos se está funcionando, vou escolher um simulador do iPhone, você pode colocar qual simulador quiser.

[14:04] Nós vamos rodar o nosso projeto. Ele vai subir o simulador. Nós temos aqui uma tela e aparentemente ele não mostrou nada. Repare que temos algumas linhas, é a tabela que colocamos, a tableView.

[14:27] Mas aparentemente ele não interpretou esses dois métodos que colocamos aqui. Isso acontece porque nós precisamos criar uma configuração adicional, ou seja, precisamos de alguma forma associar que essa tabela que nós colocamos aqui no storyboard está ligada a esses dois métodos que nós colocamos.

[14:51] Como fazemos isso? Eu vou selecionar a tabela que nós acabamos de criar no storyboard. De alguma forma precisamos criar uma referência dessa tabela no nosso ViewController.

[15:03] Quando precisamos criar essa referência, nós chamamos isso de outlets. Como eu crio uma referência dessa tabela no ViewController? Eu seleciono a tabela e clico nessa opção no canto superior direito, que é o nosso “Spector” e eu escolho a opção "Spector > Assistant".

[15:25] Ele vai dividir a tela em dois, do lado esquerdo eu tenho o storyboard e do lado direito eu tenho o meu código.

[15:35] Eu vou criar a referência no meu código, vou apertar a teclar “Ctrl” do meu teclado, clico e arrasto para o meu código. Eu vou chamar, por exemplo, de viagensTableView e clicar em "Connect".

[15:57] Eu criei uma conexão da tabela no “ViewController.swift”, vou abri-la. O que eu preciso fazer? Eu preciso dizer que essa tabela vai implementar esse protocolo de TabelViewDataSource.

[16:11] Eu vou pegar a viagensTableView, que é o outlet que acabamos de criar. Ele tem uma propriedade chamada dataSource, viagensTableView.dataSource.

[16:21] Qual é o dataSource dessa TableView? É o próprio Controller: viagens.dataSource = self. Eu vou rodar novamente o projeto e nós vamos conferir se já está tudo OK - "Stop > Play".

[16:38] Olhe só que legal, temos aqui a listagem simples com as configurações da TableView! Uma coisa que eu queria mostrar para vocês é que é muito comum hoje em dia os desenvolvedores, nos projetos que você pegar, o protocolo de dataSource não estar junto com a definição de classe.

[17:00] A galera acaba criando umas extensões, ou seja, eu posso fazer isso: posso criar uma extensão da minha classe de extension ViewController: e implementar o protocolo de UITableViewDataSource {.

[17:18] Eu passo esses dois métodos para baixo; seleciono da linha 19 até 29, copio e colo na linha 21. Fica assim.

[17:25] Não muda em nada o funcionamento do projeto, é a mesma coisa; mas é outra forma de você separar todos os protocolos que você for utilizando dentro do seu “ViewController.swift”.

[17:37] Você acaba deixando um pouco mais organizado. Se for um projeto grande, que você vai ver que vai ter vários protocolos, você pode criar uma extensão de implementação para cada protocolo para ficar mais legível e mais fácil de você achar cada pedaço.

[17:53] Vou rodar novamente só para você ver que está funcionando da mesma forma, vou clicar em "Play".

[17:58] Nós temos aqui a nossa primeira lista de viagens!

@@03
Para saber mais: Ferramentas de design

Iniciamos um novo projeto chamado Alura Viagens e começamos a desenvolver a primeira tela do aplicativo. No nosso caso, estamos copiando um layout pronto no qual são passadas todas as especificações, como cor, tamanho, fonte etc.
Se você já trabalha em uma empresa de desenvolvimento, provavelmente atua junto a uma equipe de design. Há diversas ferramentas, como Zeplin, Figma, entre outros, que nos auxiliam no entendimento do projeto, com base em prototipagem e especificações da funcionalidade.

No nosso projeto já temos todas as especificações e, à medida que o projeto for avançando, vamos implementar mais funcionalidades ao projeto.

@@04
Implementando UITableView

Durante a aula, acompanhamos a implementação de um componente chamado UITableView, muito utilizado na listagem de objetos, para montar a tela do aplicativo de acordo com o nosso projeto.
Por que precisamos implementar o protocolo UITableViewDataSource na classe ViewController?

@@Porque precisamos customizar a célula que será exibida na TableView.
 
Alternativa correta
Implementamos esse protocolo para acessar comportamentos, por exemplo o clique em cima de um item da lista.
 
Alternativa correta
Porque obrigatoriamente precisamos implementar pelo menos dois métodos para a TableView funcionar.
 
Alternativa correta! Há vários métodos que nos auxiliam na criação e comportamento de uma TableView. Porém, dois são obrigatórios: um onde configuramos o número de linhas e o outro onde criamos uma célula para ser exibida.

05
Faça como eu fiz: Entendendo protocolos

Durante o desenvolvimento do nosso projeto, teremos de lidar com protocol, que é uma estrutura muito utilizada em Swift. Um protocolo pode ser definido basicamente por um conjunto de métodos ou propriedades.
De que maneira o protocolo é importante no nosso projeto?

No momento que implementamos a UITableView, obrigatoriamente precisamos implementar o protocolo UITableViewDataSource, que nos habilita a utilizar 2 métodos:
func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return secaoDeViagens?[section].numeroDeLinhas ?? 0
}COPIAR CÓDIGO
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        guard let celulaViagem = tableView.dequeueReusableCell(withIdentifier: "ViagemTableViewCell") as? ViagemTableViewCell else {
            fatalError("error to create ViagemTableViewCell")
        }

        return celulaViagem
}COPIAR CÓDIGO
Onde:

numberOfRows: Número de linhas que a tabela terá.
cellForRow: Criação da célula que a tabela terá.

@@06
O que aprendemos?

Nesta aula, aprendemos:
Implementação da UITableView
A TableView é um componente muito utilizado e também muito poderoso para se trabalhar com a listagem de elementos. Nesta aula, implementamos apenas alguns métodos de vários disponíveis nos protocolos de UITableViewDelegate e UITableViewDataSource.

Conseguimos controlar vários estados e eventos, por exemplo, clique em um item da TableView, seleção de múltiplas linhas, drag and drop e muito mais.

https://github.com/alura-cursos/alura-viagens-constraints/archive/cdc6fee05e89f5b1dd09fb7a22dcdd27d7e05b57.zip

@02-Cabeçalho do aplicativo #1

@@01
Projeto da aula anterior

Se você deseja começar o curso a partir desta aula, pode fazer o download do projeto desenvolvido até o momento.

@@02
Criando o header

[00:00] De volta com o nosso projeto, nós acabamos de criar a lista onde nós ainda estamos mostrando somente uma mensagem qualquer, mas já temos uma lista.
[00:11] Agora é hora de nós avançarmos com a próxima etapa, que é a criação do cabeçalho do nosso projeto, ou seja, do header. Nós temos aqui, basicamente, uma view azul com uma label e um banner.

[00:31] Nós vamos começar criando uma nova view para encaixarmos dentro do header da nossa TableView. Eu venho na pasta principal do projeto, clico com o botão direito em "AluraViagens > New File".

[00:52] E agora nós vamos criar uma nova view para o nosso projeto! Eu vou selecionar a opção “View”, que está dentro da seção interface builder, “User Interface”, na verdade. Vou clicar em “Next”.

[01:08] Ele pede um nome para a nossa view. Qual nome eu vou colocar? Eu vou colocar "HomeTableViewHeader". “Home” porque é a tela inicial, a tela principal do nosso aplicativo; e “TableViewHeader”, que é a nomenclatura que daremos para o nosso header.

[01:31] Cliquei em "Criate". Ele traz aqui uma view como se fosse a tela realmente de um iPhone, só que se você for perceber, nós precisamos de uma view menor, uma view pequena para encaixarmos na parte de cima da nossa listagem.

[01:50] Começaremos redimensionando essa view. Eu tenho as medidas que vamos utilizar: a largura de 414 e a altura 300. Como eu faço para redimensionar uma view? Eu clico em cima dela e abro as opções de configuração da view no “Show the Size inspector”, no canto superior direito.

[02:13] Cliquei e ele me trouxe várias opções. Eu vou selecionar a opção onde eu tenho esse size inspector e vai me trazer a largura e altura. Como eu faço para alterar essas opções? Repare que eu não consigo mexer.

[02:32] Eu venho em “Show the Attributes Inspector” e clico no campo de “Size” e coloco a opção “Freeform”. Quando eu clico nessa opção “Freeform”, eu consigo colocar a altura que eu quiser. Vamos só checar a altura. Nós temos uma altura de 300, então onde está 896 eu vou colocar 300.

[02:56] Já tenho um espaço muito mais parecido como o que nós precisamos criar e agora eu vou alterar a cor de fundo. Como eu faço para alterar? Eu tenho aqui a cor branca e eu quero deixar azul.

[03:10] Cliquei em cima da view e eu vou selecionar a opção de cor de fundo, ou background color, e vou ter várias opções. Eu vou clicar em "Background color > Custom", que é uma cor customizada que utilizaremos.

[03:27] E ele me pede uma cor RGB. Eu já tenho aqui a cor para aplicarmos: 30, 59 e 119. Abri “Sublime Text". Vamos lá! Digitei 30 na linha Red, 59 na linha Green e 119 na linha Blue. [03:46] Vou só conferir - 30, 59, 119. Já temos a cor da nossa view, agora vamos colocar uma label! Vou voltar no simulador e repare que nós temos a label “alura viagens”.

[04:06] Como colocamos uma nova label na nossa view? É muito simples, basta abrirmos a opção da biblioteca de elementos nesse sinal de adição, "Library". Eu vou clicar e arrastar e label para dentro da nossa view do cabeçalho.

[04:26] Eu tenho aqui uma label, a primeira coisa que eu vou fazer é alterar o texto dessa label. Ao invés de label, vamos colocar alura viagens como está no simulador.

[04:40] Tem duas formas práticas de fazer isso: eu posso dar dois cliques sobre Label e digitar alura viagens; ou eu posso vir na seção no canto direito onde eu tenho a “Label”. E eu posso alterar aqui o texto; posso colocar qualquer coisa, que e ele vai alterar na view.

[05:06] Vou voltar o texto para alura viagens. Agora precisamos alterar o tipo de fonte e o tamanho. Eu tenho o tipo que vamos seguir. Vou selecionar “Label > Font”, onde eu tenho a parte de fonte no canto direito, eu vou clicar no “T”.

[05:29] Eu tenho a opção que já vem pré-selecionada, a default, e eu vou querer uma fonte customizada, vou clicar em custom e ele me traz várias opções, "T > Custom".

[05:44] A opção que eu tenho aqui, a que nós vamos seguir, é utilizar a fonte “Konihoor Devanagari”, vou clicar em cima dela e vou alterar o estilo para “Style > Semibold”.

[05:56] Repare que a nossa label já está com uma formatação diferente. Só vou conferir a fonte e o tamanho, 23. Como eu faço para alterar o tamanho? Eu clico novamente no “T”, onde eu tenho a opção “Size” (tamanho). Eu vou alterar para “23” e clicar em "Done" para confirmar.

[06:24] Agora o último passo é altearmos a cor da label. Vou novamente selecionar a label. Eu seleciono a opção "Color > White Color". Olhe só!

[06:39] Já temos algo parecido com o que nós estamos desenvolvendo, que é o header do nosso app. O próximo passo que veremos a seguir é como colocamos essa view dentro da nossa tabela. Vamos encaixar essa view que acabamos de criar na parte de cima da listagem das viagens que nós temos aqui.

@@03
Exibindo o header na TableView

[00:00] Nós acabamos de criar uma view que representa o cabeçalho do nosso aplicativo, essa view aqui.
[00:07] Porém, nós ainda não utilizamos ela nosso projeto, ou seja, nós ainda não configuramos a nossa tabela para que ela exiba esse cabeçalho. É isso que trabalharemos nesse vídeo!

[00:21] Para conseguirmos exibir o header do nosso aplicativo junto da nossa lista, precisamos usar basicamente dois métodos: um que se chama heightForRowAt, onde passamos a altura que configuraremos o nosso header; e o outro que se chama viewForHeader, onde de fato instanciamos o header do nosso app.

[00:46] Como fazemos para utilizar esses dois métodos? Nós vamos novamente na nossa classe de “ViewController.swift” e implementamos um novo protocolo da TableView, que nos permite fazer uso desses métodos.

[01:02] Podemos implementar basicamente em dois lugares: o primeiro é onde criamos a nossa classe, na assinatura, onde podemos colocar , UITableViewDelegate. Embaixo, implementamos os métodos - "Linha 17 > Pula duas linhas > fdafas".

[01:23] Ou podemos criar uma extensão, que é o que vamos fazer. Eu apertei “Cmd + Z” para voltar e vamos criar uma extensão igual quando implementamos o protocolo de UITableViewDataSource.

[01:40] Para manter o padrão eu vou criar uma extensão de ViewController, extension ViewController. Se você já está trabalhando com extensions para protocolo, é legal você manter esse padrão para os próximos protocolos que você for implementar.

[01:55] E qual é o protocolo que nos dá acesso a esses métodos do header da TableView? O protocolo é o UI (de user interface). Repare que sempre que trabalhamos com UIkit o prefixo de todas as palavras começa com UI, de user interface, UILabel, UITableView, UIColor e assim por diante.

[02:20] Você vai ver bastante esse UI no seu código. O nome do protocolo é UITableViewDelegate {}. Já implementei esse protocolo no nosso “ViewController.swift”.

[02:38] Repare que aqui temos uma diferença: quando implementamos o protocolo de UITableViewDataSource, ele nos obrigou a implementar dois métodos. Quais foram os métodos?

[02:50] O numberOfRowsInSection e o cellForRowAt. Ele obrigou porque são dois métodos que precisamos implementar, é o mínimo para a TableView funcionar, é o número de linhas e o conteúdo das células.

[03:05] Nesse caso, são métodos opcionais. Temos vários métodos aos quais temos acesso. Eu vou segurar na tecla “Command” e vou clicar em "Jump to Definition".

[03:20] Ele vai abrir a documentação do UIkit para esse método de UITableViewDelegate. Aqui ele vai dar vários métodos: willDisplay, willDisplayHeaderView.

[03:32] Aqui você tem uma série de métodos para diferentes situações para que você implemente na sua TableView. Nesse momento, aprenderemos dois métodos também bastantes utilizados quando você cria um header para TableView.

[03:51] O primeiro método que eu vou implementar aqui se chama viewforheader. Repare que ele já está aqui nos dando o autocomplete nesse método: viewForHeaderInSection.

[04:03] Eu aperto a tecla "Enter". Nós vamos analisar o que esse método pede, ele tem como parâmetro a TableView e o nome do método, viewForHeaderInSection. Ele pede que retornemos uma view.

[04:19] O que eu vou fazer aqui? Eu vou criar a view que nós precisamos retornar. Olhe só, eu vou criar uma nova constante, let headerView =. Como eu instancio a classe do header? Temos um pequeno problema, que eu vou explicar para você.

[04:41] Eu vou comentar essa constante. Nós precisamos acessar de alguma forma essa view que nós criamos no vídeo anterior, onde nós criamos o header, “HomeTableViewHeader.xlb".

[04:53] Como fazemos para acessarmos essa view? Precisamos de uma classe que controle essa view, igual temos quando abrimos o storyboard. Nós temos esse primeiro “ViewController.swift”.

[05:05] E nós temos uma classe que controla esse “ViewController.swift”, essa tela, que é essa aqui onde nós estamos fazendo todas as implementações.

[05:17] No header é a mesma coisa. Nós temos a view, que é a parte visual, onde colocamos cor, label, tudo que precisarmos; mas nós precisamos também ter um arquivo que controle esse header. Nós vamos criá-lo agora.

[05:31] Como eu faço isso? Vou clicar em cima da pasta “AluraViagens” com o botão direito, "AluraViagens > New File > iOS > Cocoa Touch Class > Next”.

[05:49] E em “Subclass of:” (subclasse) eu preciso que tenha a subclasse “UIView”. Se por acaso o seu XCode tiver qualquer outra classe, procurr por UIView.

[06:05] O nome da classe é exatamente o mesmo nome que nós colocamos para a view, para o nosso XIB, que é “HomeTableViewHeader.xib”. Eu vou manter o mesmo nome, “HomeTableViewHeader" e vou clicar em "Next" e "Create".

[06:26] Ele criou uma nova classe, que é uma UIView para controlar o header. Olhe só, temos uma view e temos uma classe, só que ainda não criamos nenhuma conexão entre as duas. Como fazemos para criarmos essa conexão?

[06:46] Eu vou abrir a “HomeTableViewHeader.xib", vou selecionar a view e vou abrir as propriedades na parte superior direita, onde tem o último ícone. Ele vai abrir o menu lateral direito e eu vou clicar no quarto ícone. Eu tenho uma opção onde posso setar a classe.

[07:10] O que eu coloco aqui? O nome da classe que eu acabei de criar, que coincidentemente é o mesmo nome da view, é HomeTableViewHeader e aperto a tecla "Enter".

[07:22] Digitei o nome e apertei a tecla “Enter” para ele configurar corretamente. Eu tenho a view, tenho o arquivo e acabei de fazer a conexão. Agora podemos voltar no “ViewController.swift” para terminarmos de criar a constante que nós estávamos criando.

[07:42] Aqui, como eu faço para ler a view que nós temos utilizando o XIB? Eu vou utilizar uma classe que se chama Bundle, ela traz o diretório dos nossos arquivos: Bundle.main.loadNibNamed.

[08:01] Aqui eu tenho uma série de parâmetros que eu preciso configurar, o primeiro é qual é o nome da view que eu quero que ele carregue. O nome da view é HomeTableViewHeader, eu abro e fecho uma string "HomeTableViewHeader".

[08:15] Aqui é importante que você coloque exatamente o mesmo nome que você criou, porque senão o aplicativo vai dar crash. Nesse owner eu vou colocar self, que é o próprio arquivo “ViewController.swift”.

[08:38] E esse options eu não vou utilizar, eu passo nil. Repare que ele é opcional, tem um ponto de interrogação, ou seja, ele pode ou não ter valor. Eu coloco nil. Vou tentar retornar essa view que nós acabamos de instanciar, essa constante, return headerView e apertar a tecla "Enter".

[09:01] Temos aqui um problema, ele fala que não consegue converter esse tipo para UIView, que é o tipo que precisamos retornar. Nós vamos analisar o que está acontecendo. Se eu tentar chamar o headerView aqui embaixo?

[09:19] Repare que ele me traz uma tipagem um pouco diferente. Eu tenho aqui um array, ou seja, uma lista de Any, que é um tipo genérico do swift. Além disso, é opcional; ou seja, é um tipo de estranho de trabalhar.

[09:35] Eu não posso retornar uma lista, eu tenho que retornar uma view, como ele retorna uma lista, ou seja, o arquivo HomeTableViewHeader pode ter mais de uma view - mas no nosso caso tem apenas uma.

[09:49] O que eu posso fazer aqui? Eu posso digitar .first, eu quero pegar a primeira view que ele encontrar. E eu posso fazer um casting para o tipo da classe que eu criei, que é as? HomeTableViewHeader.

[10:05] Agora sim, ele detecta isso como uma UIVew, porque se abrirmos o arquivo veremos que ele de fato é um UIView. Como nós acabamos de fazer o casting para HomeTableViewHeader, fica tudo certo no nosso método.

[10:23] Já configuramos o primeiro método, agora temos que configurar o segundo! Olhe só, o segundo método é a altura do header, é heightForHeaderInsection.

[10:35] Ele espera que eu retorne um tipo CGFloat - é um tipo de estrutura de swift, mas na verdade, nós precisamos retornar a altura do header. Qual é a altura mesmo? Vamos conferir abrindo o “HomeTableViewHeder". Eu selecionei a view , abri as propriedades e vi que nós temos uma altura de 300, é esse o valor que precisamos configurar nesse método.

[11:03] Vou digitar return 300. Será que já está tudo funcionando? Vou rodar o projeto e nós vamos conferir essa implementação.

[11:15] Olhe só, ele subiu o simulador, mas não mostrou a view de header que nós criamos! O que acontece aqui? Uma dica: sempre que você fizer uma implementação utilizando algum protocolo, você rodar o projeto e não acontecer nada significa que provavelmente, quase certeza, você se esqueceu de setar o protocolo, ou seja, você esqueceu-se de configurar esse protocolo.

[11:40] O que eu quero dizer com isso? Quando nós implementamos o protocolo de UITableViewDataSource, nós precisamos falar que a nossa TableView está configurando DataSource para o arquivo de ViewController.

[11:54] Precisamos fazer a mesma coisa com o protocolo de Delegate. Implementamos o protocolo e os métodos, porém não configuramos a TableView para isso.

[12:09] Como eu faço? Digitando viagensTableView.delegate = self. Agora sim, eu estou falando que a minha TableView vai implementar os protocolos de delegate nesse arquivo; ViewController, que é das linhas 35 até 46.

[12:27] Vou rodar novamente o projeto... E olhe só, nós temos aqui o header do app! Ainda está bem diferente do que precisamos implementar, mas nós já estamos dando alguns passos em direção a essa estrutura, a esse layout que implementaremos.

[12:51] Agora precisamos continuar a implementação com o header, estilizando as labels e utilizando as imagens necessárias para conseguirmos chegar nesse resultado.

@@04
Para saber mais: Protocolo UITableViewDelegate

O delegate é um design pattern que permite a comunicação entre o objeto e sua implementação. Muito útil para impedir que outros objetos conheçam o tipo concreto de uma classe, por exemplo.
A TableView, segundo a documentação da Apple, nos permite configurar cabeçalhos e rodapés de uma seção, excluir e reordenar células, além de realizar outras ações em uma visualização da tabela.

No nosso caso, utilizamos o protocolo para configurar a View que será exibida no header do aplicativo.

https://developer.apple.com/documentation/uikit/uitableviewdatasource

@@05
Implementando UITableView

Durante essa aula, fizemos a implementação do header (cabeçalho):
Cabeçalho do aplicativo Alura Viagens. Na parte inferior, há um retângulo dividido em duas partes: lê-se “Aproveite o verão, com ofertas exclusivas, somente no nosso app” à esquerda e uma imagem de pôr-do-sol à direita.

Qual método utilizamos para instanciar a View do header para exibir na TableView?

https://caelum-online-public.s3.amazonaws.com/2095-ios-layout/02/aula2_img1.png

tableView: UITableView, heightForHeaderInSection
 
Alternativa correta
tableView: UITableView, cellForRowAt indexPath: IndexPath
 
Alternativa correta
tableView: UITableView, viewForHeaderInSection
 
Alternativa correta! O método viewForHeaderInSection é um método de UITableViewDelegate utilizado para configurar qual View será exibido no header da TableView.

@@06
Estilizando os elementos do header

[00:00] Continuando, nós acabamos de configurar nossa TableView para que ela exiba o header que nós acabamos de criar, mas ainda temos bastante trabalho pela frente porque, como você pode perceber, nosso header está bem diferente do layout proposto.
[00:14] Vamos começar a analisar alguns detalhes importantes para começarmos a resolver nesse vídeo. Primeiro: nós temos uma parte branca, a parte superior, que nós precisamos corrigir.

[00:30] E nós temos também um banner flutuante, que é o segundo ponto que vamos atacar nesse vídeo. Vamos começar corrigindo esse espaço em branco.

[00:40] O que faremos? Primeiro eu vou no “Main.storyboard” e vou redimensionar a Table View para que ela ocupe todo o espaço. Agora a altura da Table View é a mesma altura do Controller.

[00:58] Além disso, se eu rodar o projeto, "Play". Repare que ainda não vamos corrigir todo o problema - vai ficar uma parte branca, que é a safe area, a área segura que nós temos nos nossos devices da Apple.

[01:14] Para corrigirmos isso, precisamos setar a cor de fundo para a cor que queremos - no caso, a mesma cor do header. Dá a impressão que é a mesma view. Eu venho no “ViewController.swif” e altero a cor de fundo da view. "Linha 19" view.backgroundColor =.

[01:34] Lembre-se sempre que quando nós trabalhamos com UIKit, todos os componentes começam com o prefixo “UI” - UIColor, UILable, UIButton e assim por diante. Nesse caso, quando queremos alterar a cor de fundo é UIColor.

[01:51] E eu vou inicializar procurando o construtor onde eu passo o RGB: (red: CGFloat, green: CGFloat, blue: CGFloat, alpha: CGFloat).

[01:58] Qual vai ser a cor? A mesma cor que nós setamos na view do header, é (red: 30.0/255.0, green: 59.0/255.0, blue: 119.0/255.0, alpha: 1).

[02:19] Agora vamos começar a mexer no header! Outro ponto que temos que analisar em relação a esse banner flutuante é a seguinte: para dar esse efeito de banner flutuante, ou seja, banner em cima do header, precisamos de um espaço vazio, conforme eu estou mostrando aqui no simulador.

[02:44] Só que a forma com que construímos o header, nós apenas alteramos a cor de fundo. Repare que nós não temos esse espaço em branco disponível para que ele fique com esse efeito.

[02:57] Qual é a ideia? A ideia é criarmos uma view azul um pouco menor para sobrar esse espaço em branco e criarmos a nossa view, que será o nosso banner. Essa é a ideia.

[03:13] Repare que na nossa implementação a altura do header realmente está maior do que nós estamos vendo aqui no outro simulador, ou seja, vamos diminuir a altura dessa view azul para que ela sobre um espaço em branco e assim consigamos dar esse efeito de sobreposição.

[03:36] A primeira coisa que eu vou fazer é voltar a cor de fundo de azul para branco. Vou abrir as configurações, em “Background” no menu lateral direito, e vou alterar para “White Color”.

[03:50] Repare que a label ficou invisível porque ela também é branca, mas daqui a pouco arrumaremos. Eu vou logo em seguida colocar uma nova view, que vai ser a * azul. Vou clicar no sinal de adição no canto superior direito, vou colocar a nova view e clicar e arrastar para a view.

[04:14] As margens esquerda e a direita têm que estar bem posicionadas porque elas ocupam todo o espaço. A altura dessa view vai ser 250. Eu posso alterar a altura através dessa parte do menu, o “Show the Size Inspector”.

[04:37] Apertei a tecla “Enter” e ele já ficou com um espaço menor do que era antes. Logo em seguida, eu vou alterar a cor de fundo para azul novamente, "Configurações > Background > Default". Eu tenho aqui a cor 30, 59 e 119.

[04:59] Agora eu vou colocar a nossa label alura viagens, que é o título do app, dentro dessa view do header. Repare que nós temos uma hierarquia de views - temos a view principal, temos uma label e a outra view que é o header view que acabamos criar, essa view azul.

[05:21] O que eu vou fazer? Eu vou clicar na label e vou arrastar ela para dentro da hierarquia do header.

[05:28] Ela está dentro. Agora basta posicionar a label acima novamente. Nós temos uma view um pouco menor. Repare que agora nós temos aqui esse espaço que precisamos para criarmos o nosso banner.

[05:53] Logo em seguida, já vamos criar o banner. Eu vou colocar uma nova view - "Library > View > Clicar e Arrastar para a tela". Repare que eu não vou colocar ela dentro do header view, vou colocar ela do lado de fora.

[06:13] E agora eu vou redimensionar o tamanho dessa view. Vou novamente no “Size Inspector” e vou alterar o tamanho, "Show the Size Inspector". Eu tenho aqui o tamanho 375 de largura e 130 de altura. Tecla "Enter".

[06:44] Como eu faço para reposicionar? Eu posso clicar e arrastar, ou eu posso utilizar a seta do teclado. Qual é a vantagem do teclado? Arrastando, eu corro o risco de clicar e colocar ela dentro da hierarquia da view - o que eu não quero.

[06:59] Então se eu coloco ela para o lado de fora, outra forma é dar dois cliques em cima da view na parte da hierarquia, que eu consigo apertar a seta do teclado para centralizar a view da forma que eu quero. Eu vou só renomear a view na hierarquia para "Banner View". [07:24] Qual é a vantagem de eu nomear os meus elementos na hierarquia? Isso facilita bastante porque à medida em que o projeto for crescendo e tiver vários componentes, vai ser muito mais fácil você achar o que você quer se eles estiverem nomeados corretamente aqui.

[07:40] Sempre que possível, deixe seus elementos com o nome para ficar mais fácil de você achar. Vamos continuar, nós temos aqui a parte esquerda, que é outra view, com uma cor verde claro; e do lado direito, uma UIImageView. Vamos colocar esses elementos agora.

[08:06] Vou novamente no library. Eu vou procurar por view e vou arrastar a view para cá, "Library > View > Clicar e Arrastar".

[08:14] E eu tenho aqui uma view com a largura de 200. Vou alterar a cor de fundo para verde claro, "Background Color > Custom > 81 > 179 > 177".

[08:38] Alterei aqui a cor, eu só vou reposicionar porque, repare que ficou um pouco mais para baixo do que eu preciso. Eu clico nela e venho com a seta até preencher todo o espaço.

[08:55] E do outro lado, na parte direita, eu vou colocar uma imagem. Clicando no sinal de adição, vou procurar por "Image View". Arrasto para o lado direito e agora eu vou redimensionar a view para que ela ocupe o espaço restante. Eu clico e diminuo o espaço.

[09:17] Basicamente, a estrutura do header nós já criamos! O que faremos agora? Vamos criar alguns outlets. O que é isso mesmo? A referência dos nossos objetos na view no nosso código. Quando precisarmos alterar a cor, o tamanho ou o título da label, nós já teremos a referência dos nossos elementos.

[09:41] Como eu faço para criar a referência? Eu vou na opção “Adjust Editor Options > Editor Options > Assistant" e ele divide a tela: o lado esquerdo com a view e o lado direito com o arquivo que controla a view. Repare que aqui já vem com alguns comentários.

[10:06] Eu vou apagar. "Seleciona > Apaga". Eu vou criar os outlets "Linha 12" // MARK: -IBOutlets. Como eu faço isso? Clico em cima do elemento, seguro a tecla “Ctrl” do Mac e arrasto para o lado esquerdo.

[10:24] Em “Name” eu vou digitar tituloLabel e agora vou criar também o outlet dessa view azul. Seguro a tecla “Ctrl” e arrasto para cá. O nome vai ser "headerView".

[10:46] Uma dica bacana de nomenclatura é a seguinte: óbvio, se você já está trabalhando em um projeto que está seguindo uma nomenclatura, continue essas regras que você tem no seu projeto; mas se você ainda não tem ou se você vai criar o seu projeto, é muito comum você colocar o nome do seu componente.

[11:07] Por exemplo: essa label é o título, título seguido do tipo, que é label. Essa view azul, por exemplo, é uma UIView, é o tipo da view. Eu coloco o nome dela, que é header e seguido do tipo. Fica headerView.

[11:27] Por exemplo: a imagem é uma Image View, eu vou colocar aqui, por exemplo, banner. Eu sei que é a imagem do banner, seguido do tipo, bannerImageView e assim por diante.

@@07
Faça como eu fiz: Configurando o header

Nesta aula, aprendemos a configurar o header da TableView através do protocolo UITableViewDelegate. Esse protocolo fornece uma série de métodos para diversos eventos que veremos mais adiante, entre eles alguns métodos que nos permite configurar o header corretamente.

Opinião do instrutor

Para configurar o header, implementamos o protocolo UITableViewDelegate e os seguintes métodos:
func tableView(_ tableView: UITableView, viewForHeaderInSection section: Int) -> UIView? {
    let headerView = Bundle.main.loadNibNamed("HomeTableViewHeader", owner: self, options: nil)?.first as? HomeTableViewHeader
    headerView?.configuraView()

    return headerView
}COPIAR CÓDIGO
func tableView(_ tableView: UITableView, heightForHeaderInSection section: Int) -> CGFloat {
    return 300
}

@@08
O que aprendemos?

Nesta aula, aprendemos:
Cabeçalho da TableView
Adicionamos uma View customizada como cabeçalho (header) da TableView. É um recurso muito utilizado em diversos apps, pois, além de ser um espaço para colocar a logomarca do app/produto, também podemos adicionar funcionalidades, como uma busca para filtrar as viagens rapidamente.

@03-Cabeçalho do aplicativo #2

@@01
Projeto da aula anterior

Se você deseja começar o curso a partir desta aula, pode fazer o download do projeto desenvolvido até o momento.

https://github.com/alura-cursos/alura-viagens-constraints/archive/ff264749e1df38905902e507e9c13e48a5bc41c6.zip

@@02
Iniciando com as constraints

[00:00] Continuando, nós acabamos de fazer algumas alterações no header - como, por exemplo, nós criamos os outlets para alguns elementos; como a label de título, o header e o banner.
[00:14] Criamos também o método configuraView onde estamos setando uma cor de fundo para o header, que é a cor azul escuro que nós utilizamos no header. E nós estamos chamando esse método no ViewController no método viewForHeaderInSection.

[00:34] Ou seja, no método onde nós instanciamos o header para ser exibido na TableView. Aqui nós temos a linha onde nós instanciamos. E embaixo chamamos esse método.

[00:47] Eu vou rodar o projeto para testarmos e vermos como ele está ficando... E aqui temos alguns detalhes para vermos. A barra superior continua com a faixa branca. Vamos voltar no “Main.storyboard” e vamos voltar o tamanho da “Viagens Table View” até a área segura. Repare que ele tem algumas linhas que nos auxiliam a encontrarmos esse espaçamento.

[01:18] Cliquei e arrastei até esse ponto. Eu vou rodar o app de novo. Nós vamos verificar essa alteração.

[01:29] O outro ponto que eu queria comentar é o seguinte: nós temos esse banner com uma view na parte esquerda e uma imagem que ainda não setamos nenhum valor, ou seja, por isso que está branco na parte da direita.

[01:45] Mas o que é importante notarmos é que na margem lateral esquerda temos um espaçamento e na margem lateral direita nós não temos. Só que se voltarmos na view, no XIB do header, repare que aqui nós temos a margem tanto na lateral esquerda quanto na lateral direita. Vamos em “HomeTableViewHeader.xib".

[02:06] Por que ele não está respeitando essas margens? O primeiro ponto é o seguinte: nós estamos rodando o projeto, nós estamos testando nosso projeto no iPhone 8. Se formos perceber, aqui embaixo nós estamos desenhando a view na visualização do iPhone 11.

[02:28] Ou seja, eles possuem tamanhos diferentes, é por isso que às vezes o tamanho que você desenha não vai refletir em algum simulador que você por acaso vier a testar.

[02:43] Quer dizer que eu tenho que desenhar uma view para cada tamanho de iPhone? Na verdade, não. Ainda bem que não! Esse é o ponto principal do curso que nós vamos começar a comentar agora: o auto layout.

[02:58] Com o auto layout, como o próprio nome já sugere, nós conseguimos setar algumas configurações nas views para que ela se redimensione automaticamente, ou seja, vamos construir um único layout para que ele funcione em todos os tamanhos de iPhones.

[03:19] O que precisamos começar a entender? Tem algumas formas de trabalharmos com auto layout no iOS. Nesse caso, nós estamos falando do framework UIKit, e uma delas se chama constraint - é essa técnica que nós vamos explorar ao decorrer desse curso.

[03:39] O que é uma constraint? Uma constraint nada mais é do que uma regra que adicionamos em uma view para que ela entenda de que forma ela deve se comportar. Como eu adiciono essas regras? Como eu adiciono uma constraint em uma *view?

[03:58] Vamos começar a engatinhar nesse tema e você vai ver que não é difícil. Nós temos que ter alguns cuidados que eu vou comentando com vocês ao decorrer do curso.

[04:10] Primeiro: eu quero configurar a minha view azul, essa view do header, para que ela se estique nas laterais independentemente do tamanho do iPhone - se ele for pequeno ou grande, ela vai se esticar.

[04:24] Ou seja, eu preciso prender essa view na margem lateral esquerda e na margem lateral direita, para que ela se redimensione não importando o tamanho que seja o dispositivo. Vamos começar a trabalhar nesse sentido!

[04:44] Vou selecionar a view. O primeiro passo para se trabalhar com uma constraint é selecionar o elemento que você quer adicionar essa constraint, ou seja, o elemento que você quer adicionar essa regra de auto layout.

[04:59] Pronto, já selecionei! O que eu preciso fazer agora? Eu preciso entender onde fica o painel de pin, ou seja, onde é o painel onde eu consigo pinar minha view aos lados que eu quero que ela se estique.

[05:13] Esse painel fica na parte inferior do Xcode. Nós vamos utilizar esse ícone de adicionar novas constraints, “Add New Constraints”. Quando eu clico em cima desse botão ele abre um menu parecido com esse.

[05:32] O que eu quero fazer? Eu quero começar prendendo minha view ao topo, então eu clico na parte superior do ícone, onde eu indico que estou prendendo minha view ao topo. Quando eu deixo ele selecionado, ele fica com esse vermelho mais escuro; quando eu clico de volta, eu tiro a seleção e não estou fazendo nada.

[05:52] Eu quero pinar minha view ao topo. Clico no ícone. Por enquanto nós não vamos explorar as outras opções. Eu clico no botão de adicionar constraint, “Add 1 Constraint”.

[06:03] Cliquei no botão. A primeira coisa que temos que entender é que quando colocamos uma constraint e ele fica com as linhas laterais vermelhas, significa que possuímos pelo menos um ou mais problemas com as constraints.

[06:24] Veremos aos poucos como fazemos para resolver esses problemas. O que eu preciso entender? Que eu acabei de pinar minha view acima. Agora eu quero pinar minha view na lateral esquerda e na lateral direita. Vamos continuar colocando outras funções.

[06:43] Agora que eu já sei onde é o painel das constraints, eu vou clicar em “Add New Constraints” e vou colocar uma constraint na margem lateral esquerda e na margem lateral direita.

[06:54] Coloquei as constraints e agora clico em "Add 1 constraint"... A minha view ainda continua com erros de constraint! Agora vamos entender como analisamos esses erros. Como eu faço? Nesse menu da lateral esquerda, na view que eu estou mexendo, a “Home Table View Header”, tem esse botão vermelho.

[07:21] Eu vou clicar nele. Esse botão indica que a view possui erros com as constraints. Eu clico nele e ele me fala qual é o erro. Ele falou que precisa de constraints para altura, ou seja, eu preciso adicionar constraints para altura.

[07:41] Quando eu adiciono uma view no meu plano de desenho das views, do storyboard, eu preciso, na verdade, satisfazer algumas regras - e quais são essas regras? Abri o Sublime Text. Basicamente, eu preciso indicar qual é o eixo y.

[08:03] Eu tenho o eixo “X” e o eixo “Y”, o eixo “Y” na vertical e o eixo “X” na horizontal. Eu preciso indicar nesse plano onde essa view vai ficar. “INDICAR QUAL É O EIXO Y”, na próxima linha "INDICAR QUAL É O EIXO X", depois "CONFIGURAR ALTURA” e “CONFIGURA LARGURA".

[08:23] Basicamente, precisamos sempre satisfazer essas condições, indicar qual é o eixo “Y” e o eixo “X”, configurar a altura e a largura. Quando colocamos a view pinada acima, nós já estamos dizendo qual é o eixo “Y”.

[08:45] Quando eu prendo a view, tanto na lateral esquerda quanto na lateral direita, eu já estou dizendo qual é a largura. Não estou dizendo o tamanho fixo da largura, mas se eu prendo ela ao lado esquerdo e prendo ao lado direito, ele já sabe calcular a largura.

[09:05] Agora eu só preciso indicar qual é a altura! Eu vou abrir novamente o painel das constraints, clicando em "Add New Constraints". Repare que aqui eu posso setar uma largura fixa.

[09:16] Nesse caso, não precisamos porque já pinou o lado esquerdo, o lado direito; mas eu preciso indicar qual é a altura marcando a opção “Height". A altura é 250 mesmo, então eu clico em "Add 1 constraint".

[09:30] E olhe que bacana, quando eu faço isso a minha view já não possui nenhum erro de constraint! Ou seja, todas as condições que nós comentamos estão certas, nós conseguimos configurar e nos enquadrarmos nessas regras de constraint.

[09:54] Demos o primeiro passo para entendermos como as constraints funcionam e acabamos de comentar que podemos pinar a view para que ocupe o espaço disponível. Ainda falta configurarmos constraints para os outros elementos - que é o que faremos a seguir!

@@03
Configurando constraints

[00:00] Nós acabamos de adicionar constraints na view do header e agora continuaremos adicionando outras constraints para resolvermos o problema do banner.
[00:13] Nós temos a parte lateral esquerda onde temos o espaçamento, esse espaçamento não está sendo respeitado na margem lateral direita. O que vamos fazer? Nós precisamos adicionar constraints no banner. Eu vou começar selecionando o banner, ele ainda não tem constraints.

[00:35] Aliás, como eu sei se uma view tem constraint ou não? É muito simples! Eu vou pegar como exemplo a view que nós acabamos de mexer, a view do header que tem constraints.

[00:47] Mas como eu sei? Quando eu seleciono a view, tem duas formas. Uma é percebendo se essa view possui algumas linhas ou guias. Eu vou dar um zoom para facilitar a visualização.

[01:00] Repare que quando eu passo o cursor do mouse, ele aponta algumas linhas que mostram que essa view possui constraints. Essa é uma forma.

[01:12] Como a view está com a cor azul igual a linha das constraints, fica um pouco difícil de visualizar, mas tem uma forma que não falha. É através do menu “Show the Size Inspector” no menu lateral direito.

[01:26] Eu vou selecionar a view mais uma vez... Selecionei. Se eu clico na opção “Show the Size Inspector”, ele automaticamente abre um menu de constraints, se tiver constraints. Nesse caso, tem. Ele indica quais são as constraints que essa view possui.

[01:45] Isso que é legal porque você consegue ver claramente quais são as constraints que foram aplicadas. Olhe só, tem uma constraint na margem lateral esquerda, uma constraint na margem lateral direita, uma constraint ao topo e uma constraint de altura.

[02:04] Se eu clicar na constraint de altura, ele vai falar qual é a constraint de altura. Se eu clico na constraint acima, ele mostra que é a constraint de topo. Essa é uma forma rápida e simples de verificar se uma view possui constraints ou não.

[02:22] Agora que nós já sabemos, vamos voltar para o banner. Eu cliquei no banner no menu esquerdo. Repare que aqui no menu “Show the Size Inspector” ele não mostra nada relacionado às constraints, ou seja, essa view ainda não possui.

[02:37] Utilizaremos basicamente a mesma lógica que utilizamos na view do header, que é pinar a view ao lado esquerdo e ao lado direito. Só que ao invés de pinarmos a view acima, pinaremos a view na parte debaixo do header. Esse é um conceito muito importante para começarmos a entender.

[03:02] Sempre que pinamos a nossa view, ou seja, sempre adicionamos constraints a alguma view em relação a alguma outra coisa, nós estamos colocando uma constraint em relação ao header.

[03:19] Vamos prendendo e amarrando as coisas. Tem pontos positivos e tem pontos negativos, vamos entender isso aos poucos. Eu vou começar selecionando o banner. É importante começarmos de fato a colocar as constraints, termos certeza qual view estamos selecionando.

[03:42] Por exemplo: se sem querer eu clico no meio e acho que estou selecionando a view do banner. Na verdade, eu não estou; eu estou selecionando a view lateral esquerda do banner. Se eu clico do outro lado, eu estou selecionando a imagem.

[03:57] Repare que clicando é difícil de encontrar a view do banner. É por isso que, muitas vezes, é mais interessante você utilizar o menu lateral esquerdo, onde você consegue selecionar de fato diretamente a view que você quer.

[04:12] Por isso, é importante nós colocarmos nomes que nos indique de fato qual componente estamos trabalhando. É uma boa prática mantermos tudo nomeado porque à medida que o projeto vai crescendo vai ficando difícil de encontrar os elementos.

[04:31] O que eu quis dizer com isso? Que às vezes é mais fácil você selecionar com o mouse e às vezes é mais fácil você selecionar as coisas no menu lateral esquerdo. Nesse caso, eu selecionei através do menu.

[04:45] Nós começaremos adicionando algumas constraints. Tem duas formas de adicionar constraints através da interface builder. A primeira já aprendemos no vídeo anterior, que é com o menu das constraints. Eu clico no ícone do menu das constraints no lado inferior direito.

[05:00] Eu clico e consigo de fato saber onde eu quero colocar as constraints - no lado esquerdo, no lado direito, abaixo ou acima. É uma das formas.

[05:12] A outra forma é com o ponteiro do mouse; só que para utilizar essa forma, eu preciso selecionar a view, eu preciso pressionar a tecla “Ctrl” do teclado.

[05:28] Repare bem, a tecla “Ctrl”, não é a tecla “Command”. No Mac temos duas teclas semelhantes, mas temos que pressionar a tecla “Ctrl”. Pressionei a tecla “Ctrl” e eu vou adicionar constraints em relação a essa view do header. Olhe só o que eu vou fazer. Clico e pressiono, clico naview e arrasto para o lado esquerdo.

[05:57] Repare que ele me diz na parte lateral direita o nome da view, “HomeTableViewHeader”, ou seja, é nessa view mesmo que eu quero adicionar as constraints. Ele abre um menu com várias opções.

[06:11] Eu tenho aqui diversas opções de constraints. Nós vamos tentar entender o que é cada uma. “Leading Space to Safe Area”, “Bottom Space to Safe Area”, “Trailing Space to Safe Area” e “Top Space to Safe Area”. Por enquanto nós vamos analisar essas quatro opções.

[06:27] O que quer dizer “Leading Space to Safe Area”? Aqui, quando vamos adicionar constraints e trabalhar com auto layout, é muito comum vermos essas duas palavras, leading e trailing.

[06:40] Traduzindo leading, para entendermos de uma forma mais fácil, é a margem lateral esquerda. Sempre que você ver essa palavra, leading, significa “margem lateral esquerda”. Sempre que você ver essa palavra trailing saiba que é a margem lateral direita. Leading é esquerda e trailing é direita.

[07:04] Nesse caso, queremos pinar - ou seja, adicionar constraints - na margem lateral esquerda. Eu vou clicar em "Leading Space to Safe Area". A mesma coisa com o outro lado. Eu seguro a tecla “Ctrl” e arrasto para a parte branca na direita.

[07:22] A parte branca é onde estamos selecionando header todo, não é a parte azul. Agora vamos adicionar constraints na margem lateral direita, por isso escolheremos clicar em "Trailing Space to Safe Area".

[07:38] Ainda possui alguns erros de constraints. Nós vamos clicar na bola vermelha no menu da esquerda para analisarmos quais são esses erros.

[07:47] Ele fala que a view precisa da posição “Y”. Lembra que temos o eixo “X” e o eixo “Y”? Prendemos as duas views na margem lateral esquerda, leading, e na margem lateral direita é trailing.

[08:04] Agora vamos prender essa view em relação à view do header, a view azul. O que vamos fazer? Eu selecionei mais uma vez a view do banner. Vou segurar a tecla “Ctrl” e vou arrastar, dessa vez naview azul, para a header view - não é na parte branca, é na parte azul.

[08:34] Soltei e ele abriu várias opções novamente. Como eu quero prender na parte debaixo dessa view azul, eu vou escolher a opção “Bottom”.

[08:49] E eu ainda tenho erro de constraint! Agora eu preciso adicionar a altura, vou no botão de bolinha vermelha na frente de “Home Table View Header” no menu da lateral esquerda.

[08:57] Eu vou selecionar a view do banner e vou setar uma altura. Vou abrir o painel de constraints e vou selecionar a altura. Clico em “Height > Add 1 constraint".

[09:12] E está tudo azul, estão com as constraints funcionando. Muito legal! Uma coisa que percebemos aqui é que a view ficou acima do que estava, ou seja, quando nós setamos a constraint na parte debaixo, grudamos o nosso banner na parte debaixo da view azul.

[09:36] Só que, na verdade, não queremos que ele fique exatamente no mesmo nível, queremos que ele fique um pouco mais abaixo, como estava. O que eu vou fazer? Eu vou selecionar o banner e vou editar uma constraint.

[09:51] É muito importante sabermos adicionar uma constraint, apagar e editar. Selecionei o banner e agora com o menu “Show the Size Inspector” selecionado, eu vou descer um pouco e vou verificar quais constraints foram aplicadas.

[10:16] Margem lateral esquerda, margem lateral direita, parte inferior e a altura. Essas foram as constraints. Eu quero editar a constraint inferior, eu quero que ela fique um pouco mais para baixo. Eu seleciono a constraint e dou dois cliques no ícone "Align Bottom to: Header View".

[10:36] Cliquei duas vezes e ele vai me levar para outro menu. Qual é o campo em que eu edito o valor da constraint? É o campo chamado “Constant”. A constraint está com um valor 0, mas eu posso alterar esse valor.

[10:56] Eu vou posicionar a view ao lado para nós conseguirmos visualizar rapidamente o que está acontecendo. Se eu colocar um valor negativo, ele vai subir mais. Eu vou colocar -10, por exemplo... Ele ficou mais para cima. Olhe a constraint indicando.

[11:11] Nessa constraint temos um valor de -10. Se -10 vai mais para cima e eu quero que ele vá mais para baixo, eu vou colocar 10. Quando eu coloco 10 ele fica da forma que estava antes, um pouco mais para baixo. Na hora em que formos arredondar a view você vai ver que ele vai dar aquele efeito bem legal de sobreposição.

[11:45] Já conseguimos adicionar as constraints no banner. Está tudo azul, não temos nenhum erro de constraints. Vamos fazer o build o projeto de novo para vermos se resolvemos o nosso problema.

[11:59] Olhe só, que legal! Fizemos o build e não vimos diferença nenhuma! Acalma-se, que vamos resolver o problema agora. O que acontece? Adicionamos constraints no nosso header, porém a TableView que temos no nosso ViewController não sabe onde começa, onde termina e aonde ela vai se posicionar em relação ao layout.

[12:20] Por isso não está funcionando. A ideia é prender a TableView a margem esquerda, a margem direita, no topo e na margem inferior. O que eu vou fazer? Vou selecionar a TableView. Venho no menu inferior, onde adicionamos as constraints e vou prender ela com o valor 0, ou seja, sem nenhum espaçamento em todas as margens.

[12:49] Depois que eu selecionei todas essas opções, vou clicar em "Add 3 constraints". Ele me mostra que eu prendi em todas as margens. Vou rodar o projeto mais uma vez.

[13:04] E agora, sim, temos o header com as constraints - ou seja, eu tenho a margem direita, que não estava funcionando, e a margem esquerda. Aos poucos nós vamos aplicando as constraints e vendo como o auto layout pode nos ajudar a resolver esse tipo de problema.

[13:25] Coloquei uma constraint errada. Como eu faço para apagar? Eu vou voltar na view do header. Se você já adicionou as constraints corretamente no seu banner, não precisa fazer isso.

[13:40] No meu caso, eu vou fazer só para mostrar como eu apago uma constraint. É muito simples, eu seleciono a view que quero apagar a constraint e vejo qual constraint eu coloquei.

[13:53] De repente, eu coloquei uma constraint de altura incorreta. Eu seleciono essa constraint e aperto a tecla “Delete”. Cliquei e apaguei a constraint. Como eu apaguei, ele está reportando algum erro.

[14:09] Ou eu posso colocar de novo, ou eu posso apertar as teclas "Command + Z". Vou colocar aqui mais uma vez através do menu, clico em "Height > Add 1 constraint"... Ficou tudo azul e está funcionando.

[14:24] Vamos rodar o projeto de novo! Como você pode ver, quanto mais praticamos, mais conseguimos desenvolver essa habilidade de percepção do que está dando errado, do que eu fiz que adicionou uma constraint que não era para adicionar.

[14:41] Tudo isso é prática. Nós vamos, gradualmente, dando alguns passos até que entendamos de fato como esse mecanismo de auto layout com constraints funciona.

[14:53] Nos próximos vídeos nós continuaremos praticando para ficarmos com uma habilidade melhor de percepção para resolvermos esses problemas que o auto layout nos ajuda.

@@04
Regra de aplicação de constraint

Uma das técnicas de auto layout, quando trabalhamos com o UIKit, se chama constraints. Através dela conseguimos configurar regras para determinados elementos, dizendo como devem se comportar.
De acordo com o que estudamos na aula, quais condições devemos satisfazer para estar em conformidade com as regras das constraints?

Configurar 'eixo x', 'eixo y', altura e largura.
 
Alternativa correta! Via de regra, é necessário configurar a posição x e y, altura e largura. Altura e largura não precisam necessariamente ser valores fixos. Podemos, por exemplo, estabelecer a margem esquerda e direita que automaticamente o auto layout vai entender que a largura pode ser dinâmica.
Alternativa correta
Configurar o 'eixo x' e 'eixo y'.
 
Alternativa correta
Configurar a altura e largura.

@@05
Adicionando constraint no banner

[00:00] Acabamos de colocar a constraint no banner, em toda essa view, colocamos a constraint lateral esquerda, direita, abaixo e da altura. Porém, os elementos de dentro, que é essa view na margem esquerda, e a imagem ainda não possuem constraints.
[00:19] A ideia desse vídeo é colocarmos as constraints nesses dois elementos e também vermos alguns cuidados que temos que ter com algumas constraints específicas.

[00:33] Como já aprendemos, temos duas formas práticas de colocarmos constraints: uma é segurando a tecla “Ctrl” e arrastando para onde eu quero pinar; a outra é através do menu inferior. Dependendo do caso, você pode escolher uma forma ou outra.

[00:52] Nesse caso, como eu estou selecionando a view à esquerda e eu quero pinar ela acima, abaixo e a esquerda, como eu não consigo visualizar a view que está abaixo dela para poder pinar, é mais fácil utilizar o menu inferior.

[01:10] Se a view por acaso tiver ficado com uma borda, você não precisa fazer. Eu estou fazendo isso somente para mostrar para você. Puxei a view para baixo e para a direita.

[01:20] Se a view estivesse assim, ficaria mais fácil; porque eu seguraria a tecla “Ctrl” e conseguiria arrastar para a view utilizando o mouse a tecla “Ctrl” ou o trackpad do Mac.

[01:34] Clicando e arrastando eu conseguiria facilmente pinar em direção à view que eu quero. Como ela ocupa todo o espaço, eu não tenho como visualizar onde ela está.

[01:49] Nesse caso, é mais fácil utilizar o menu inferior para conseguir pinar minha view. Dependendo do caso, você utiliza ou o cursor do mouse com a tecla “Ctrl” pressionada, ou o menu de constraints na parte inferior da tela.

[02:05] Como eu coloco uma constraint? Clico na view, na label ou em qualquer elemento que herda de UIView e em seguida abro o menu das constraints.

[02:19] Eu vou começar pinando a minha view na margem inferior. Ele está com um valor de 2, mas, na verdade, deveria ser 0. Na margem esquerda também, 0. E ao topo, 0.

[02:35] Ou seja, ele vai ficar bem colado abaixo, a esquerda e acima. Uma coisa importante é a seguinte: ou podemos mostrar qual é a altura para a view explicitamente. Se eu quisesse setar uma altura, não precisaria preencher a margem em cima e abaixo, estaria falando qual é a altura explicita dessa view.

[03:07] Ou você pode pinar a view acima e abaixo. Prendendo a view acima e abaixo ele consegue calcular a altura automaticamente. Eu não preciso dizer explicitamente qual é a altura porque implicitamente ele vai saber calcular a atura dessa view.

[03:26] Nas regras da constraints, como conversamos nos vídeos anteriores, precisamos indicar o eixo “Y”, o eixo “X”, a altura e a largura. Nem sempre precisaremos explicitamente falar qual é a largura e a altura porque, nesse caso, como eu estou prendendo ao topo e abaixo, ele mesmo calcula a altura.

[03:46] Ou eu pino, ou eu mostro a altura explicitamente; depende do caso. Nós veremos quais cuidados temos que ter ao deixarmos altura e largura fixas daqui a pouco.

[04:02] Recapitulando, prendemos acima, a esquerda e abaixo. Agora eu vou clicar em "Add 3 Constraints". Estamos adicionando regras na nossa view para que ela saiba como se comportar quando o layout se esticar ou diminuir.

[04:20] Temos problemas. Como eu sei que nós temos problemas? Porque ele está indicando linhas vermelhas. Sempre que você clicar em uma view e tiver linhas vermelhas, significa que essa view tem problema com as constraints.

[04:39] É até uma dica: se você for fazer uma entrevista de emprego e precisar fazer um teste, tem que tomar muito cuidado para você não entregar o seu projeto prático com problemas nas constraints. Uma das coisas que a galera analisa é se o candidato tem esse conhecimento com auto layout.

[05:03] Você precisa entender direito como aplica o auto layout e sempre deixar as constraints aplicadas corretamente. Eu tenho problemas com as constraints. Na verdade, ele vai pedir para setar um valor de largura. Como eu sei que é largura? Porque ele me diz que precisa de constraints para a largura.

[05:25] O que faremos para solucionar? Vamos clicar na view e vamos aplicar constraints para largura. Eu venho no menu inferior e adiciono uma constraint para largura. Clico em "Add 1 constraint".

[05:42] Repare que no começo você vai adicionando constraint, vai vendo qual mensagem a interface builder te dá, você vai acertando e de repente você precisa apagar uma constraint.

[05:54] No começo é assim mesmo, até você pegar prática e entender direito como aplica. Como acabamos de colocar a constraint de largura, ele já não está mais apontando nenhum erro.

[06:08] Faremos a mesma coisa com a imagem, a diferença é que vamos prender a imagem abaixo, acima e a direita. Como eu faço para adicionar constraints?

[06:20] Vamos utilizar o menu inferior. Sempre que eu for adicionar uma constraint, eu preciso selecionar a view. Depois eu venho no menu inferior e adiciono, pino a view da forma que eu quiser. Eu vou prender acima, vou prender na margem direita e abaixo.

[06:46] Também está com espaçamento de 2, vamos deixar 0. Ele vai reclamar com a largura, mas eu vou adicionar sem, só para nós pegarmos o costume de lermos as mensagens que o interface builder nos dá.

[07:01] Adicionei a constraint, cliquei em "Add 3 constraints". A view ficou vermelha, ou seja, nós temos problemas. Vamos ver qual é o problema que essa view está tendo com as constraints! [07:14] Ele fala que precisa da posição do eixo “X”. Por que essa mensagem está um pouco diferente? Ou setamos a largura, ou indicamos qual é a posição do eixo “X”. Nesse caso, como aprendemos na margem de trailing, ou seja, na margem direita, acima e abaixo; podemos setar a largura.

[07:41] Eu venho no menu inferior e seto a largura, marcando a opção “Width". Nós temos aqui as duas views com as constraints. Eu vou rodar o projeto no simulador do iPhone 8... Vamos ver como ele está, está subindo o simulador.

[08:03] Parece que ele respeitou, de fato, a regra que aplicamos! Uma coisa importante é a seguinte: nós, como desenvolvedores e desenvolvedoras, temos que ter uma leitura ampla do projeto.

[08:21] Temos que sempre nos perguntar: "esse layout vai funcionar para iPhone e para iPad?" Precisamos entender o todo para sabermos como configuramos o auto layout.

[08:36] Por que eu falei isso? Porque a ideia desse aplicativo especificamente é ele funcionar para todas as versões de iPhone e também para iPad. Eu vou fazer o build o nosso projeto em um iPad. Olhe só, aqui em cima onde eu tenho o simulador de todos os devices disponíveis, ele está mostrando o iPhone 8.

[08:58] Mas eu posso selecionar outros devices como, por exemplo, os iPads. Vou selecionar o iPad Air, por exemplo. Selecionei e vou clicar para ele gerar um build. Nós vamos ver como o nosso layout está se comportando em um iPad.

[09:20] Já dá para vermos algumas coisas do auto layout que configuramos, outras nós veremos que temos problemas.

[09:29] Olhe só, que bacana! Qual é o ponto positivo até agora? O ponto positivo é que essa view em que nó aplicamos as constraints, a view do banner e do header, realmente está se esticando.

[09:45] Aplicamos isso em um iPhone, quando ele renderizou no iPad, ele se esticou de acordo com a largura do device. Lembra quando pinamos a view a esquerda e a direita? Na verdade, é para isso, é para ele se esticar ou diminuir de acordo com a necessidade. Isso funcionou.

[10:06] O que não está tão bacana? Dentro do banner, setamos uma constraint de largura nessas views e aparentemente ele não soube bem administrar isso. Aqui não está aparecendo a imagem, mas provavelmente a imagem ficaria bem pequena também, porque deixamos a largura fixa.

[10:33] Alguns minutos atrás, nesse mesmo vídeo, eu falei que veríamos alguns problemas com constraints com valores fixos, principalmente largura e altura - esse é um deles, temos aqui um problema porque setamos um valor de largura fixo.

[10:49] Só que a view não tem, na verdade, uma largura fixa; ela tem que ficar larga ou menos larga de acordo com a largura da view pai.

[10:59] Então nós acabaremos trabalhando um pouco com proporcionalidade. Ao invés de deixarmos um valor fixo, falaremos que a largura dessa view é tanto um valor proporcional a largura da view pai. Trabalharemos com o multiplier.

@@06
Proporcionalidade - Multiplier

[00:00] Legal! O que eu quis mostrar para você aqui é: tome cuidado com larguras fixas!
[00:05] Temos o costume, eu também faço isso, de testarmos somente no simulador e, às vezes, quando testamos em um iPhone maior ou menor, ou em um iPad, vemos que o layout não está tão legal assim.

[00:21] As constraints estarem em azul não significa que o meu layout está ok para outros tamanhos. Você sempre tem que ter isso em mente, teste em outros dispositivos.

[00:38] O que eu vou fazer aqui? Ao invés de deixar uma largura fixa, que é a forma que implementamos, eu vou apagar essa constraint e setar uma largura proporcional a view do banner.

[00:52] Olhe só, que bacana! Como eu apago uma constraint? Eu clico na view que possui essa constraint, clico na linha da constraint que eu quero apagar e aperto o “Delete” no teclado.

[01:07] Repare que ele ficou vermelho. É porque nós infringimos uma regra, mas já vamos consertar. Eu vou apertar as teclas "Command + Z" para voltar.

[01:13] A outra forma de apagar é a seguinte: eu clico na view e venho no “Show the Size Inspector”, a opção da régua no canto superior direito. Logo embaixo ele me diz quais são as constraints que essa view possui.

[01:37] Nesse caso, eu quero apagar a constraint de largura. Na linha abaixo das constraints eu consigo selecionar a constraint de largura e apertar a tecla "Delete". Dá na mesma. A forma que você achar mais fácil, você executa.

[01:52] Como eu faço para setar uma largura proporcional view pai? É o seguinte: eu vou setar uma constraint de largura e vou falar que ela é igual a largura do banner.

[02:10] Nos vídeos anteriores eu disse que era muito comum trabalharmos com constraints indicando que uma view possui alguma ligação com a outra, de largura, de altura ou pinar uma view em relação a outra. É muito comum trabalharmos dessa forma.

[02:28] E esse é um exemplo prático. Eu vou falar que a view que eu tenho à esquerda está com problema de constraints, possui uma largura proporcional a view do banner. Eu vou segurar a tecla “Ctrl” e vou arrastar a view com problema para a view do banner.

[02:48] Ele vai me dar algumas constraints. Repar que algumas estão com uma bola.

[02:57] Significa que eu já apliquei, essas são as constraintsque já estão instaladas. O que me importa nesse momento é utilizar a opção “Equal Widths”, ou seja, essa view vai ter a largura igual a view banner. Eu vou clicar nessa opção. Repare que já fala que não tem problema nas constraints.

[03:26] Eu clico na seleção ao redor da view e vejo a constraint de largura. Repare que essa linha é um pouco diferente da outra.

[03:36] Ela tem esse símbolo de igualdade (=). Quando a constraint que eu utilizo o “Equal Widths”, ou “Equal Heights”, eu utilizo a constraint de igualdade e ele me mostra esse sinal.

[03:55] O que é importante eu saber aqui? É importante eu entender para que serve esse sinal de igualdade. Olhe só, vou selecionar a view e vou clicar na constraint de largura.

[04:07] No menu no “Show the Size Inspector”, eu tenho uma opção “Multiplier” (“multiplicador” em português), ele está em 0.5333333. Eu vou copiar esse valor, selecionando e apertando as teclas “Command + C". Eu vou começar a brincar um pouco com esse campo só para mostrar para você para que ele serve.

[04:31] Por enquanto nós não sabemos muito bem o que é esse valor. Eu vou apertar as teclas “Command + C” para preservar o valor, mas ele é interessante por causa disso. Se eu quiser dizer que essa view ocupa todo o espaço, eu coloco o 1.

[04:43] Se eu quiser dizer que essa view ocupa metade do espaço da view pai, 1:2 - que seria o meio. Se eu quiser dizer que essa view ocupa 1/3 do total, 1:3. Para 1/4, 1:4 e assim por diante.

[05:03] Eu consigo trabalhar com esse tipo de cálculo. Se eu utilizar o 1, ele vai ocupar tudo. Como eu quero um pouco menos que 1, eu utilizo a igualdade que já havíamos configurado quando setamos a constraint, que é 0,533333. É um pouco menos que 1. Aperto a tecla "Enter".

[05:28] E ele me dá essa opção de a view ocupar o espaço que queremos. Vamos ver se isso funciona de verdade? Vou rodar no iPad novamente. Faremos esse teste, olhe só que legal.

[05:42] Agora ele ocupa o mesmo espaço proporcionalmente ao que era do iPhone. Falta fazermos isso para a imagem também. É o mesmo processo. Eu tenho a constraint de largura que não serve para o que precisamos, vou deletar.

[06:02] O que eu vou fazer agora? Eu vou setar uma constraint de igualdade de largura. Eu seleciono a imagem, pressiono a tecla “Ctrl” e arrasto para a view que eu quero pegar como apoio, a view do banner.

[06:17] E eu escolho a largura, a igualdade de largura e a opção "Equal Widths". Cliquei e solucionei a constraint. Repare que ela ficou com uma linha e o sinal de igualdade, conforme eu havia comentado com você.

[06:33] Vou rodar de novo no iPad... Ele continua da forma que era para ficar mesmo. Agora vou rodar mais uma vez no iPhone 8, para ver se não quebrou o nosso layout no iPhone.

[06:50] Legal, nós já conseguimos acertar a view do banner tanto no iPhone quanto no iPad! A ideia principal desse vídeo era mostrar para você como utilizamos essa opção “Multiplier”, ou seja, essa largura de igualdade para resolvermos esse tipo de problema.

[07:10] E também mostrar que às vezes é meio perigoso trabalharmos com tamanho de altura ou largura fixo. É sempre bom testarmos o nosso projeto em vários simuladores para vermos se o auto layout realmente está ficando legal e está atendendo a proposta do layout que precisamos implantar.

@@07
Faça como eu fiz: Multiplier constraint

Um dos cuidados que temos de ter ao trabalhar com constraints é a configuração de tamanhos fixos (largura e altura). Conforme aprendemos, nem sempre o mesmo tamanho fica legal em um iPhone e em um iPad. Por isso, temos que aprender como utilizar tamanhos proporcionais para cada tipo de dispositivo. O Multiplier nos ajuda exatamente nisso, pois conseguimos colocar tamanhos proporcionais a visualização que estamos trabalhando.
Como usamos o Multiplier nesta aula?

Opinião do instrutor

Para configurar valores com Multiplier, é necessário selecionar a constraint no storyboard ou xib. Com a constraint selecionada, basta acessar o menu lateral direito, na opção Show the attributes inspector e em seguida configurar o valor no campo Multiplier.

@@08
O que aprendemos?

Nesta aula, aprendemos:
Configurar constraints
Através das constraints, conseguimos fazer uma série de configurações nos elementos da nossa View e, dessa forma, adaptamos o layout para que funcione em outros tamanhos de dispositivos.

Multiplier
Multiplier é muito útil para configurar um valor proporcional a outro. Ou seja, quando não queremos configurar um valor fixo, podemos dizer que ele é x em relação à View pai. Esse recurso é muito utilizado principalmente quando a View tem de se comportar em iPhones e iPads.