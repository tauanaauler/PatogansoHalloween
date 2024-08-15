
<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/203873640-a5b1a1f6-0e40-40d6-8924-f07ef055c3d2.png">
</p>

<h1 align="center"> Pata&Ganso Halloween Assombrado </h1>


`Felipe Theil` `Tauana Auler` `Grupo:Patoganso` `Profº Vini Cassol` `Disciplina Jogos Multiplayer` `UniRitter Campus FAPA`

<p align="center">
  • <a href="#conceito-do-jogo">Conceito Do Jogo</a> •
  <a href="#tecnologia-escolhida">Tecnologia Escolhida</a> •
  <a href="#análise-da-tecnologia">Análise da Tecnologia</a> •
  <a href="#primeiro-protótipo">Primeiro Protótipo</a> •
  <a href="#level-design">Level Design</a> •
  <a href="#concept-art">Concept Art</a> •
  <a href="#playtest">Playtest</a> •
  <a href="#atribuições">Atribuições</a> •
</p>

<hr><br>

## INTRODUÇÃO

<br>

### Conceito do jogo

<p align= "justify"> O jogo trará desafios cooperativos, do gênero Plataforma, sub-gênero Puzzle, no qual dois jogadores precisam desvendar quebra-cabeças e trabalhar em conjunto para prosseguir para a próxima fase. Os jogadores possuem mecânicas únicas para cada um, fazendo com que não seja possível completar os desafios individualmente.</p>

<p align= "justify">As fases serão organizadas em apenas 1 tela cada fase, não ultrapassando o limite da viewport. Desta maneira os jogadores conseguem visualizar toda a área do puzzle e não ficam divididos entre telas diferentes. Essa dinâmica é inspirada em jogos que serão usados como referência, sendo eles: Celeste, Fireboy and Watergirl, e o mod de Super Mario World chamado Mario’s Keytastrophe: Rebirth Edition.</p>

<p float="left" align= "center">
  <img height="200" src="https://user-images.githubusercontent.com/43689501/196953425-924879ae-f576-4f11-8dc9-53c68c386671.png">
  <img height="200" src="https://user-images.githubusercontent.com/43689501/196953376-abd252cc-f6eb-4776-a83b-2112a3d843bf.png">
  <img height="200" src="https://user-images.githubusercontent.com/43689501/196953463-5a8876cf-22b5-4522-bc06-3f73cbcf2095.png">
</p>

<p align= "justify"> A história está ligada diretamente a outros jogos já desenvolvidos da Série Patoganso, sendo eles: Patoganso e A Maldição dos Sapos, e Patoganso: Origens. Nessa nova história, nosso protagonista não será mais nosso carismático Patoganso, mas sim dois personagens novos e humanos, que são fãs da série de jogos. Os dois amigos estão a caminho de uma festa de Halloween, vestiram suas melhores fantasias de Pato e Ganso, mas agora terão problemas para seguir sua jornada.</p>
<br>

### Tecnologia escolhida

<p align= "justify"> A tecnologia escolhida foi a biblioteca Netcode for GameObjects para a engine Unity. A escolha foi feita com base na familiaridade dos integrantes do grupo com a engine, assim como o fato de ser uma biblioteca lançada recentemente, oferecendo soluções atualizadas de networking.</p>

<p align= "justify"> Esta biblioteca permite que os desenvolvedores foquem na construção do jogo, sem precisar se preocupar com protocolos e frameworks de  baixo nível, pois ela oferece soluções para enviar dados do mundo e objetos de jogo através de uma sessão compartilhada entre vários usuários simultaneamente.</p>

<p float="left" align= "center">
  <a href="https://unity.com"><img height="50" src="https://user-images.githubusercontent.com/43689501/196957132-f7d8b8a2-00dd-40eb-8383-ad9108b8a2d9.png"></a>
  <a href="https://docs-multiplayer.unity3d.com"><img height="50" src="https://user-images.githubusercontent.com/43689501/196958331-9b0b9816-6fbc-4669-9bd4-c199d6ab42ea.png"></a>
</p>

<br><br>

<hr>

## Análise da Tecnologia


### Netcode, o que é?

<p align= "justify">Netcode for GameObjects é uma biblioteca recentemente lançada com integração para a engine Unity. Ela consiste de soluções para estabelecimento de sessões entre múltiplos usuários simultâneos, assim como o envio de dados e objetos de jogo através dessas sessões. Desta forma, os desenvolvedores podem focar no desenvolvimento do jogo sem precisarem se preocupar com frameworks e protocolos de baixo nível.</p>

<br>

### Netcode, como instalar?

<p align= "justify">A biblioteca Netcode for GameObjects é um pacote da engine Unity, instalado diretamente na aba Package Manager da ferramenta, podendo ser instalada por nome ou por URL.</p>

<p align= "justify">Após a instalação do pacote, seus componentes estarão disponíveis para uso na seção Packages do projeto.</p>

<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/195425271-f11c5d4b-aeda-4a5b-bcfc-80bcbc86ab1d.png">
</p>

<br>

### Netcode, como configurar?

<p align= "justify">Após a instalação e com um novo projeto aberto, já é possível configurar a biblioteca para uso.</p>

<p align= "justify">Inicialmente é necessário adicionar um Gerenciador de Rede e um Unity Transport (UTP) ao projeto. É criado um Game Object vazio e nomeado GerenciadorDeRede, este objeto recebe o componente NetworkManager, do pacote Netcode, e configura-se o tipo de transporte para UnityTransport. Este objeto irá então gerenciar todas as configurações relacionadas a rede do projeto. </p>

<p align= "justify">Para que um objeto Player seja criado para cada jogador conectado, é necessário adicionar a ele o componente NetworkObject, do pacote Netcode. Deste objeto é criado um Prefab e no NetworkManager, no campo NetworkPrefabs, adiciona-se um novo slot para alocar este Prefab criado. Além disso, este Prefab é adicionado ao campo Player Prefab do NetworkManager. Desta maneira, quando cada jogador se conecta a partida, o objeto Player é criado para cada um.</p>

<p align= "justify">Inicialmente é necessário adicionar um Gerenciador de Rede e um Unity Transport (UTP) ao projeto. É criado um Game Object vazio e nomeado GerenciadorDeRede, este objeto recebe o componente NetworkManager, do pacote Netcode, e configura-se o tipo de transporte para UnityTransport. Este objeto irá então gerenciar todas as configurações relacionadas a rede do projeto. </p>

<br>

### Netcode, como executar?

<p align= "justify">Por fim, é necessário inicializar o componente NetworkManager para que as conexões sejam estabelecidas. O componente inclui três opções de inicialização:</p>

* __Start Host:__ inicializa o NetworkManager como servidor e cliente ao mesmo tempo, tornando-o um servidor ouvinte, que se conecta a outros clientes mas também possui uma cópia local do jogo;
* __Start Server:__ inicializa o NetworkManager apenas como servidor, sem ter um cliente local, para que clientes conectem-se a ele;
* __Start Client:__ inicializa o NetworkManager apenas como cliente, para poder se conectar a um servidor.

<p align= "justify">Quando um cliente é inicializado, o NetworkManager utilizará o endereço IP e a porta especificados no seu componente Transport para a conexão. Para configurar a conexão em tempo de execução, é possível utilizar o método SetConnectionData do componente NetworkManager. São definidos:</p>

* O endereço IP do servidor (ex: “127.0.0.1”, definido como string);
* A porta utilizada (ex: 12345, definido como short);
* Opcionalmente, quais endereços IP o servidor estará escutando (ex: “0.0.0.0”, definido como string).

<p align= "justify">A vantagem de definir 0.0.0.0 como “endereço de escuta” é que o servidor estará configurado para escutar todos os endereços IP do sistema local. Desta forma, é possível testar instâncias de clientes no mesmo sistema, assim como clientes de outros sistemas conectados na mesma rede local (LAN).</p>

<br><br>

<hr>

## Primeiro protótipo


<p align= "justify">O protótipo foi iniciado com a construção de uma simples tela para testes de movimentação e colisão dos jogadores, conforme a imagem a seguir.</p>

<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/196962345-e36e8924-5d75-4821-bd36-f628a93ff4ac.png">
</p>

<p align= "justify">Foram configurados alguns botões de testes para a instância de uma rede e conexão através da mesma, cada um executando uma função do componente Network Manager:</p>

* __SERVER:__ Instancia a máquina local como servidor dedicado, sem jogador local, ao qual outros clientes podem conectar-se;
* __HOST:__ Instancia a máquina local como servidor e cliente simultaneamente, permitindo que ela rode uma cópia local do jogo ao mesmo tempo que outros clientes conectam-se a ela;
* __CLIENT:__ Instancia a máquina local como cliente apenas, necessitando que haja um servidor ou host já instanciado para que este possa conectar-se.

<p align= "justify">Em seguida, foram configurados objetos Prefabs para os jogadores 1 e 2. Invés do método padrão de definir um Prefab igual para todos os jogadores através da propriedade Player Prefab do Network Manager, foi utilizado um sistema no qual o jogador Host recebe o Prefab Player1 e o jogador Client recebe o Prefab Player2, conforme a imagem a seguir.</p>

<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/196962459-4e015a86-8f3e-455c-9214-38a3e8919060.png">
</p>

<p align= "justify">Além do código que determina a lógica de criação dos objetos dos jogadores, também é necessário incluí-los na lista de objetos de rede do Network Manager. Desta forma, o Network Manager sincroniza os objetos na rede, permitindo que cada jogador tenha a visão real do estado do jogo em tempo de execução.</p>

<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/196962555-cecb9bd1-5b46-41b5-9a6d-820c9914b694.png">
</p>

<p align= "justify">A criação dos Prefabs dos objetos de tipo Player1 e Player2 foi feita de forma simples, com um script que controla sua movimentação e capacidade de pulo. A determinação das colisões entre cada jogador e cada tipo de terreno foi feita através da Layer Collision Matrix, propriedade nativa das configurações da engine Unity. Desta forma, temos objetos com os quais apenas o jogador 1 irá colidir, e outros objetos com os quais apenas o jogador 2 irá colidir, formando a base para o sistema de puzzle do jogo.</p>

<p align= "center">
<img src="https://user-images.githubusercontent.com/43689501/196962703-22c92848-d917-4ce6-8858-369cb5dfeac1.png">
</p>

<p align= "justify">Por fim, decidiu-se conceder ao cliente autoridade suficiente para atualizar sua posição no servidor, invés de utilizar o método padrão de enviar um pedido de atualização ao servidor toda vez que a posição do cliente deve ser alterada. Essa decisão foi tomada com base no tipo de jogo desenvolvido: como jogo casual cooperativo, o cliente ter certa autoridade sobre si mesmo não introduz grandes complicações. Além disso, essa decisão ajuda na performance da comunicação pela rede.</p>

<p align= "justify">Isso se torna possível graças ao componente Client Network Transform, do pacote Multiplayer Samples Utilities, que pode ser instalado através do Package Manager utilizando a opção “add from Git URL” e adicionando a seguinte URL:</p> <a href="https://github.com/Unity-Technologies/com.unity.multiplayer.samples.coop.git?path=/Packages/com.unity.multiplayer.samples.coop#main">https://github.com/Unity-Technologies/com.unity.multiplayer.samples.coop.git?path=/Packages/com.unity.multiplayer.samples.coop#main.</a>

<br><br>

<hr>

## Configurações Finais de Rede


<p align= "justify">Da mesma forma que foi concedida autoridade ao cliente quanto à posição e movimentação do personagem que ele controla, também foi concedida tal autoridade quanto às animações do personagem e certos elementos do cenário. Isto foi feito utilizando um componente chamado ClientNetworkAnimator, derivado do componente NetworkAnimator, responsável pela sincronização de estados de animação na rede.</p>

<p align="center">
<img height="300" src="https://user-images.githubusercontent.com/43689501/203873145-4c3e8c4b-af81-4782-ab67-7459f8e04b37.png">
</p>

<p align= "justify">Como pode ser visto na imagem acima, o componente possui apenas um método, o qual sobrescreve o método OnIsServerAuthoritative do componente NetworkAnimator, para fazer com que as animações não sejam sujeitas à autoridade do servidor, mas sim à do cliente.</p>

<p align= "justify">Além disso, foram configuradas maneiras de conectar os jogadores através de um rede local (LAN) utilizando os protocolos de transporte do Netcode for GameObjects. Para iniciar uma sessão de jogo, um dos jogadores deve utilizar o botão “HOST” do menu inicial. Feito isso, o outro jogador deve digitar o IP Local do host no campo de IP e então utilizar o botão “JOIN”. Desta forma, a conexão será estabelecida e os jogadores podem compartilhar a sessão de jogo. Os métodos que adicionam essas funcionalidades aos botões podem ser vistos na imagem abaixo:</p>

<p align="center">
<img height="600" src="https://user-images.githubusercontent.com/43689501/203873124-2d599a0b-e0e3-4a8b-bb13-f29ec79b52da.png">
</p>

<p align= "justify">Por fim, o método utilizado para iniciar a sessão utilizando o IP Local do host como endereço de acesso, utilizando o sistema de sockets da rede, pode ser visto na imagem a seguir:</p>

<p align="center">
<img height="300" src="https://user-images.githubusercontent.com/43689501/203873101-0e52cbda-58a6-47ce-97c0-ddfdbaa72bf3.png">
</p>


<br><br>

<hr>

## Level Design

### Elementos Interativos

<p align= "justify">Os elementos interativos são objetos e/ou parte do cenário com os quais o jogador pode interagir, seja empurrando, acionando ou pressionando. Cada elemento terá sua peculiaridade e alguns deles terão restrição de interação com um ou outro jogador, o que será decidido futuramente.</p>

<p align= "justify">Os elementos definidos foram:</p>

* __Plataforma sólida__ (implementado);
* __Plataforma "pular-através"__; (Descontinuado)
* __Plataforma rotatória__ (implementado);
* __Botão:__ Um jogador deve manter ele pressionado fazendo peso (implementado)
* __Alavanca:__ Similar ao botão, mas permanece ativada mesmo que o jogador se afaste; (Descontinuado)
* __Plataforma fantasma:__ Uma plataforma que perde solidez caso o jogador fique muito tempo em cima dela. (implementado)


### Fases

<p align= "justify">Com a ideia inicial da história e mecânicas principais, moldou-se a progressão das fases, bem como rascunhos para as mesmas. Ficando definido inicialmente que o jogo terá 3 fases e tela única de fase que não translada nem divide. O objetivo foi criar uma progressão na dificuldade em escapar da fase, tornando o puzzle intrigante e atrativo para o jogador continuar até o final. </p>

<p align= "justify">Com isso, para a curva de aprendizagem ao longo das fases, foi projetado o seguinte:</p>

* __Fase 1:__ Jogadores devem encontrar uma chave para abrir uma porta trancada. Introduz plataformas sólidas e pular-através, botões e alavancas, espinhos à vista;
* __Fase 2:__ Jogadores devem encontrar uma forma de arrombar uma porta. Introduz plataforma fantasma, espinhos escondidos, plataforma rotatória;
* __Fase 3:__ Jogadores devem encontrar uma forma de contornar uma parede sólida, sem porta. Não possui chão, plataforma fantasma age como forma de cruzar o penhasco, plataforma rotatória age como obstáculo acima do penhasco.

<p align="center">
<img height="400" src="https://user-images.githubusercontent.com/43689501/199617850-28e5db39-57ed-43aa-81ec-8a1a86b8a01f.png">
</p>

<p align="justify">Na imagem acima, podemos ver um rascunho da ideia sobre a terceira fase. A parte em preto é uma seção oculta que só pode ser acessada ao encontrar a entrada, neste local o jogador possui baixa visão, em uma espécie de labirinto vertical precisa encontrar a saída para o outro lado da fase. </p>

<p height="200" align="center">
<img src="https://user-images.githubusercontent.com/43689501/199617861-a47af9d7-a3ef-4a47-ba85-a282db8406c4.png">
</p>

<p align= "justify">Na imagem acima, há um exemplo de como poderia ser utilizado botões em conjunto com espinhos e plataformas. Neste rascunho, o jogador azul aciona um botão, ele faz com que ao mesmo tempo espinhos subam do chão e uma plataforma de elevação desça. O objetivo nessa situação é fazer com que o jogador em vermelho acerte o timing entre pular e não ser acertado pelos espinhos. </p>



### Versão Final das Fases

<p align= "justify">A versão final do Level Design das fases também sofreu algumas alterações para se adaptar ao tempo de entrega. Com isso foi necessário cortar o uso de alavancas e espinhos, e montar utilizando apenas plataformas normais, plataforma elevatória, plataforma fantasma e paredes. Todos os elementos podem ser acionados com botão de pressão.</p>

<p align= "justify">Podemos ver abaixo o rascunho para as fases 1, 2 e 3, respectivamente. E logo em seguida, a versão final implementada com assets.</p>

<p float="left" align= "center">
  <img height="150" src="https://user-images.githubusercontent.com/43689501/203872457-6758ee88-500b-4299-9884-317562379d58.png">
  <img height="150" src="https://user-images.githubusercontent.com/43689501/203872474-066aed0e-14a0-48a2-b01d-e6ab1bd5d307.png">
  <img height="150" src="https://user-images.githubusercontent.com/43689501/203872480-5f5ceb25-fd52-476c-9ef6-5427a3044e53.png">
  
  <img height="400" src="https://user-images.githubusercontent.com/43689501/203872487-83919396-8285-4fb3-9b46-83b4a2d69b61.png">
  <img height="400" src="https://user-images.githubusercontent.com/43689501/203872498-903a7efd-85ce-40e6-b91a-68d382966f7f.png">
  <img height="400" src="https://user-images.githubusercontent.com/43689501/203872502-7bc7d601-b31a-4935-aa78-2a20d2d55e5b.png">
</p>


<br><br>

<hr>

## Concept Art

### Personagens

<p align= "justify">Foi definida a Concept para cada um dos personagens pensando em ter silhouetas bem marcadas e cores bem distintas, para que eles sejam reconhecíveis em qualquer situação. Como dito anteriormente, um personagem está fantasiado de Pato e outro de Ganso, suas fantasias fazem referência ao visual de Patoganso em outros jogos da franquia.</p>

<p align= "center">
<img height="300" src="https://user-images.githubusercontent.com/43689501/199618899-1547478f-6514-4178-9850-5b36d8663c62.png">
</p>

<p align= "justify">A baixo, imagens do protagonista Patoganso em Origens (esquerda) e Maldição dos Sapos (direita) que fazem referência às fantasias dos protagonistas do jogo. </p>
<p float="left" align= "center">
<img height="150" src="https://user-images.githubusercontent.com/43689501/199619802-24221370-4a3c-4bed-8e86-671b66b24534.png">
<img height="150" src="https://user-images.githubusercontent.com/43689501/199620335-45b31ed6-e174-4787-8dee-69f0db51183b.png">
</p>

<p align= "justify">Como há elementos de cena que interagem exclusivamente com um personagem somente, é necessário que os personagens possuam uma identidade bem definida, em relação à cores e silhueta. Desta maneira, o design da Pata foi pensado com um tom de pele escuro e a silhueta utilizando círculos, já o Ganso, possui um tom de pele claro e apesar dos cantos arredondados, utilizou-se mais retângulos e triângulos, sua altura também contribui para o diferenciar da outra personagem.</p>

<p align= "justify">A paleta de cores sofreu pequenas alterações desde sua versão inicial. Foi aplicado uma técnica de Hue Shifting para que as cores alcançassem espectros mais próximos ao roxo, deixando com um clima mais adequado ao tema, que é o Halloween.</p>

<p align= "center">
<img height="400" src="https://user-images.githubusercontent.com/43689501/203872264-592da099-0386-4960-b186-e9c533702017.png">
</p>


<br><br>

<hr>

## Playtest

![image1](https://user-images.githubusercontent.com/43689501/203872770-452ad7e6-4f9c-402e-93ee-48b3480b8725.png)

<p align= "justify">Para a condução do playtest em sala de aula, foi montado o protótipo da Fase 1, visto na imagem acima. Os jogadores foram instruídos quanto ao objetivo do jogo e os comandos básicos de movimento e pulo. Com a realização do playtest, foram coletados feedbacks positivos sobre os seguintes pontos:</p>

* Jogabilidade e level design;
* Puzzles e gameplay cooperativo;
* Arte e identidade visual;
* Nível de dificuldade.


<p align= "justify">Além disso, foram elencados os seguintes pontos para melhoria:</p>

* Colisão entre personagens e cenário;
* Clareza do objetivo dos jogadores;
* Clareza do funcionamento dos botões;
* Clareza sobre qual jogador possui a chave;
* Física dos pulos;
* Movimentação das plataformas giratórias;
* Interação com botões.


<p align= "justify">Baseado nos feedbacks coletados, as seguintes mudanças foram implementadas:</p>

* O jogador passar a ter seu pulo efetuado completamente ao pressionar a tecla, sem necessidade de segurá-la pela duração do pulo;
* Foi adicionado um “coyote time” ao pulo do jogador, que permite-o realizar um pulo por um curto período de tempo após cair de uma plataforma;
* O jogador passa a interagir com os botões simplesmente ao caminhar por cima deles, sem necessidade de pular;
* Correção de bug onde, em certos casos, o jogador ficava preso na colisão do terreno;
* Adição de HUD mostrando qual dos jogadores possui a chave;
* Mudança no tamanho e arte da porta;
* Mudança nas cores de botões, plataformas e paredes para indicar visualmente quais botões estão ligados a quais elementos do cenário.


<br><br>

<hr>

## Atribuições

* “Skeletal Waltz Theme”, by Wolfgang licensed CC-BY 4.0 https://opengameart.org/content/skeleton-waltz-theme;
* “Shadow Tag – sneaky cartoon music with bursts of liveliness”, by Audio Hero licensed Zapsplat Standard License https://www.zapsplat.com/music/shadow-tag-sneaky-cartoon-music-with-bursts-of-liveliness/;
* “Fundo gradiente para celebração de halloween”, Imagem de Freepik https://br.freepik.com/vetores-gratis/fundo-gradiente-para-celebracao-de-halloween_31155933.htm.


![image8](https://user-images.githubusercontent.com/43689501/203873298-c631a699-c6a2-4999-94af-362ea4bf1001.png)

<br><br>

<hr>

<p align="center">Confira outros jogos dos mesmos criadores de Patoganso! <br><br>
<img src="https://user-images.githubusercontent.com/43689501/194366648-135a583c-b511-4722-a8e1-d316dfde6d19.svg" alt="Confira os jogos da Série Patoganso" style="height: 41px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" >
</p>
<p align="center">
<a align="center" href="https://uattau.itch.io/" target="_blank"> <br>uattau.itch.io</a>
</p>

<p align="center">
<a align="center" href="https://gtheil.itch.io/" target="_blank"> gtheil.itch.io </a>
</p>
