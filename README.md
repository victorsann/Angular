<div align="center">
 <img src="./assets/logo-nav@2x.png">
</div>

<br>

Angular é uma framework de design de aplicativos e plataforma de desenvolvimento para a criação de single page application eficientes e sofisticados.

Esta documentação tem por função auxiliar no aprendizado e uso da estrutura Angular e de sua plataforma de desenvolvimento, desde seu primeiro aplicativo até a otimização de single page applications complexas.

<h1>Caracteristicas Básicas</h1>

Assim como qualquer plataforma de desenvolvimento, o Angular possui uma estrutura com características próprias e funcionalidades específicas. Estas incluem:

- Uma estrutura de desenvolvimento baseada em components
- Uma collection de bibliotecas que abrangem uma variedade de features, incluindo roteamento, gerenciamento de fomulários, comunicação client-server e muito mais
- Um conjunto de ferramentas de desenvolvimento para ajudar a construir, testar e atualizar seu código. Sendo uma delas a Angular CLI

<h1>Ambiente de Desenvolvimento</h1>

O ambiente de desenvolvimento necessário para utilizar o Angular demanda algumas instalações, portanto, para criar este ambiente, siga o passo a passo a seguir:

<h2>Node.js</h2>

Aplicações Web demandam o uso de uma série de recursos para diferentes funcionalidades, como packages e libs específicas. O Javascript, e por consequência aplicações que fazem uso deste, contam com o NPM(Node package manager) para tal. Que nada mais é quem um host de inúmeros packages que são essenciais para criar uma aplicação. Dada essa necessidade, a documentação a seguir mostra como obter o Node, além de definir algumas características sobre o mesmo:

<h2>Typescript</h2>

Como já foi citado, o Angular é desenvolvido sobre a estrutura do Typescript(TS), sendo este um Superset do famoso ECMAScript. O TS é visto como uma otimização do Javascript, sendo mais robusto e se adequando a aspectos mais populares aos desenvolvedores. A inclusão da Orientação a Objetos, por exemplo, torna possível a definição de variáveis tipadas, a criação de classes, e o uso dos demais aspectos da POO, sendo uma das principais adições ao Javascript. O TS também é utilizado em outras ferramentas, como o React, além de aplicações server-side desencolvidas em Node. Para instalar e fazer uso da linguagem, acesse o cmd da sua máquina e use o comando a seguir:

    npm install -g typescript

Para mais informações sobre o Typescript acesse: [typescript.org](https://www.typescriptlang.org/).

<h1>Endentendo o Angular</h1>

<h2>Angular CLI</h2>

A Angular CLI é a ferramenta que permite a criação dos projetos e o gerenciamento das development tasks do Angular, como teste, bundling e deployment. Para obter a Angular CLI e fazer uso de seus recursos, acesse o cmd da sua máquina e use o comando a seguir:

    npm install -g @angular/cli

Após o fim da instalação, verifique se tudo ocorreu bem no processo através do comando a seguir:

    ng --version

Tendo como resultado esperado:

         _                      _                 ____ _     ___
        / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
       / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
      / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
     /_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
                    |___/


    Angular CLI: 11.2.11
    Node: 14.16.1
    OS: win32 x64

    Angular:
    ...
    Ivy Workspace:

    Package                      Version
    ------------------------------------------------------
    @angular-devkit/architect    0.1102.11 (cli-only)
    @angular-devkit/core         11.2.11 (cli-only)
    @angular-devkit/schematics   11.2.11 (cli-only)
    @schematics/angular          11.2.11 (cli-only)
    @schematics/update           0.1102.11 (cli-only)

<h2>Criando uma Aplicação</h2>

O desenvolvimento de aplicações Angular é feito no contexto de um workspace customizável, que por padão, já possui uma estrutura mínima para uso, e essa estrutura será utilizada no processo de entendimento dos conceitos essenciais do framework. O workspace, por sua vez, será abordado de forma aprofundada no futuro.

Para criar uma aplicação Angular do zero, torne a acessar o terminal de comando e rodar o comando a seguir no diretório desejado:

    ng new my-app

A Angular-CLI irá solicitar algumas configurações básicas para seu projeto, como o uso de strict e do Angular routing, além de qual style sheet será utilizado. Porém, no momento, estas configurações não irão interferir no entendimento dos próximos assuntos, logo, podem ser escolhidas sem nenhuma especificidade.

Para executar a aplicação, acesse o diretório criado(my-app) e execute o comando a seguir:

    ng serve --open

Uma nova janela será aberta no navegador, nela a aplicação será lançada localmente. O resultado é uma estrutura básica de template, meramente explicativa. Ela será posteriormente substituída, então fique a vontade para modificá-la como bem desejar.

<h1>Project Structure</h1>

Com uma aplicação em mãos, é importante se fazer ciente de como a mesma se divide, as funcionalidades e a razão da existência dos diretórios e arquivos que a compõem. A diante faremos um overview sobre os mais importantes dentre eles:

<!-- <h2>node_modules</h2>

A <b><i>node_modules</i></b> é uma folder comum a aplicações que fazem uso do Javascript, sendo basicamente um repositório de funcionalidades úteis aos desenvolvedores. Ela conta com uma série de pacotes e bibliotecas com inúmeros packages que são gerenciados pelo NPM, manager sobre o qual falaremos mais a frente.

<h2>src</h2>

A <b><i>src</i></b> é a main folder da aplicação. É nela que são estruturados todos os componets e módulos, além da estrutura de routing, style sheet e é onde está o index.html do projeto. Ela se divide nas pastas e arquivos a seguir:

<h2>app</h2>

A app folder carrega consigo o que seria o main component ou o main module do projeto. Nela temos acesso a file de routing da aplicação e ao controle de modules, além dos arquivos que compõem qualquer módulo em geral:

<h3>app-routing.module.ts</h3>

Este arquivo só estará presente na sua versão caso você tenha definido a instação do Angular routing ao criar o projeto. É nele que definimos as rotas e seus respectivos components.

<h3>app.component.css</h3>

É o arquivo onde definimos o style sheet de um módulo em específico. Com isso é possível ter uma estrutura desacoplada e components separados.

<h3>app.component.html</h3>

Consiste no template único que cada component possui, e mantém a mesma lógica de estrutura desacoplada citada acima.

<h3>app.component.spec.ts</h3>

É o arquivo de teste unitário que cada component precisa ter para ser incluído na estrutura do Karma.conf.js.

<h3>app.component.ts</h3>

O app.component.ts age como um controller, sendo nele declarada a classe @Component, os métodos e propriedades que definem o comportamento de um component.

<h3>app.module.ts</h3>

Arquivos de gerenciamento dos modules que correspondem as partes do projeto. Todos os modulos e importações da aplicação são declarados no app.module.ts.

<h3>assets</h3>

É o diretório que permite manipular arquivos extras que serão usados na aplicação, como imagens, fontes e entre outros.

<h3>environments</h3>

A pasta de environments, ou ambientes, basicamente identifica em que ambiente a aplicação está em run, se em produção(environments.prod.ts) ou desenvolvimento(environments.ts). A única diferença entre esses arquivos é a atribuição que é dada a variável <b>production</b>, que é logicamente true para produção e false para desenvolvimento.

<h3>index.html</h3>

Arquivo de marcação root definido na angular.json file, onde toda a aplicação começa a ser renderizada.

<h3>main.ts</h3>

Arquivo principal da Solution, definido na angular.json file.

<h3>polyfills.ts</h3>

Arquivo que age como um tradutor, com o qual é possível utilizar recursos do ES6, por exemplo, em navegores que só compilam o ES5, além de várias outras funcionalidades.

<h3>styles.css</h3>

Arquivo de style sheet global da aplicação.

<h3>test.ts</h3>

O test.ts é exigido no karma.conf.js e carrega recursivamente todos os arquivos .spec do framework.

<h3>.browserslistrc</h3>

O arquivo <b>.browserslistrc</b> é utilizado pelo build system para ajustar tanto CSS quanto Javascript aos navegadores listados. Esses navegadores são:

    last 1 Chrome version
    last 1 Firefox version
    last 2 Edge major versions
    last 2 Safari major versions
    last 2 iOS major versions
    Firefox ESR

O browserslistrc também permite verificar quais versões dos navegadores são contempladas pela Angular CLI. Para isso, use o comando a seguir:

    npx browserslist

O resultado deve ser próximo ao seguinte:

    npx: installed 6 in 3.665s
    and_chr 92
    and_ff 90
    and_qq 10.4
    and_uc 12.12
    android 92
    baidu 7.12
    chrome 92
    chrome 91
    chrome 90
    edge 92
    edge 91
    firefox 91
    firefox 90
    firefox 89
    firefox 78
    ie 11
    ios_saf 14.5-14.7
    ios_saf 14.0-14.4
    kaios 2.5
    op_mini all
    op_mob 64
    opera 78
    opera 77
    safari 14.1
    safari 14
    safari 13.1
    samsung 14.0
    samsung 13.0

<h3>.editorconfig</h3>

A <b>.editorconfig</b> é um gerenciador de configurações de texto, que ajuda a manter padrões de escrita e identação consistentes para multiplos desenvolvedores trabalhando no mesmo projeto em IDEs distintas.

<h3>.gitignore</h3>

O <b>.gitignore</b> é utilizado no processo de gerenciamento de versão de um projeto. Cada identificador listado neste arquivo define que seu correspondente no diretório será ignorado caso um commit seja feito.

<h3>angular.json</h3>

O <b>angular.json</b> configura o workspace padrão citado anteriormente. É basicamente um json que relaciona e identifica cada arquivo da estrutura, onde são citadas a versão do projeto e entre outras informações.

<h3>karma.config.js</h3>

O <b>karma.config.js</b> é uma biblioteca utilizada para a criação de testes unitários desenvolvida pela própria equipe do Angular. Ela trata todos os arquivos spec nos vários components.

<h3>package-lock.json</h3>

O <b>package-lock.json</b> descreve as dependências usadas no projeto, dando informações como a versão instalada, links de verificação da integridade dessas dependências, dentre outras coisas.

<h3>package.json</h3>

O <b>package.json</b> é um arquivo de configuração utilizado para estipular e configurar as dependências do projeto, além de listar estruturas importantes como os scripts que podem ser executados dentro da aplicação e dividir dependencies de devDependencies.

<h3>tsconfig.app.json... </h3>

Tanto o <b>tsconfig.app.json</b> quanto os arquivos subsequentes são arquivos que configuram o Typescript e diferentes escalas dentro do porjeto. -->

<h1>Guia de Desenvolvimento</h1>

A seguir estão listados os principais temas necessários para desenvolver uma aplicação em Angular:

- [Modules](https://github.com/victorsann/Angular/blob/master/content/modules.md)
- [Components](https://github.com/victorsann/Angular/blob/master/content/components.md)
- [Templates](https://github.com/victorsann/Angular/blob/master/content/templates.md)
- [Directives](https://github.com/victorsann/Angular/blob/master/content/directives.md)
- [Dependency Injection](https://github.com/victorsann/Angular/blob/master/content/dependency_injection.md)
- [Routing and Navigation]()
- [Forms]()
- [HTTP client]()
- [Testing]()
- [Testing]()
