<h1>@Component</h1>

Components são os blocos que sustentam uma aplicação. Um component inclui uma TypeScript class com um <b><i>@Component()</i></b> decorator, um template HTML e um style sheet. O decorator <b><i>@Component()</i></b> define as seguintes especificações:

- Um template HTML que instrui o Angular a como rederizar o component
- Uma classe Typescript que define seu comportamento
- Um seletor CSS que define como o component será utilizado em um template
- Um CSS set opcional que define a aparencia que será dada aos elementos do template HTML

A seguir temos um exemplo da estrutura mínima de um Angular component:

    import { Component } from '@angular/core'

    @Component({

     Selector: 'my-component',
     templateUrl: '<h2>Hello World</h2>',

    })

    export class MyComponent {

      constructor() {}

    }

<h3>Selector</h3>

O selector define a posição de uso de um component dentro da árvore de objetos DOM, o referenciando através de uma tag HTML que leva sua marcação, tornando este <i>Child</i> daquele que contenha esta tag. Essa componentização permite criar a árvore de componentes que define a view da aplicação. A imagem a seguir ilustra como essa estrutura funciona:

<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/131503957-228fad00-e5ea-45ea-a73c-e620f977cdcf.png">
</div>

Para incluir o exemplo anterior dentro da árvore de objetos DOM, usariamos seu selector da seguinte forma:

    <my-component></my-compinent>

Dentro do template onde fosse declarado, ele seria renderizado da seguinte forma:

    Hello World

<h3>Class</h3>

O Angular possui uma forte presença da Orientação a Objetos em sua estrutura, sendo assim, uma das partes mais importantes de um component é a sua classe, cuja função é definir todo e qualquer comportamento que ele virá a ter. As classes Typescript são nomeadas seguindo a convensão de nomenclatura <i>camelCase</i>, além é claro da palavra-chave <i>class</i> e do modificador <i>export</i>, que possibilita a importação desta em outras partes da aplicação:

    export class MyComponent {

        constructor() {}

    }

Para quem tem certo conhecimento em POO, a definição de um constructor já é bastante familiar. Porém, os cosntructors de uma classe Angular não se restringem a inicialização de classes ou de objetos, elas são de suma importância no processo de dependency injection, sobre o qual falaremos mais a frente.

<h2>@Input & @Output</h2>

Tanto o @Input quanto o @Output definem mecanismos de comunicação entre components chamados parents e um ou mais child component. Sendo o @Input() responsável por permitir que um parent component faça updates em um child component, já o @Output() permite que child components enviem dados para seus parents.

    import { Input, Output } from ‘@angular/core’;

    @Input({

    bindingPropertyName?: string

    })

    @Output({

    bindingPropertyName?: string

    })
