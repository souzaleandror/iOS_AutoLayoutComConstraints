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