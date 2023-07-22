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
PRÓXIMA ATIVIDADE

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