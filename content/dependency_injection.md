<h1>Dependency Injection</h1>

<h2>@Injectable</h2>

O conceito de injeção de dependências é bastante conhecido dos que possuem certa experiência com desenvolvimento, e é bastente comum nos frameworks mais modernos. Não sendo uma exceção no Angular, que possui o decorator <i>@Injectable</i> para tal funcionalidade. O exemplo a seguir mostra a estrutura base de uma classe Injectable:

    import { Injectable } from '@angular/core';


    @Injectable({
      ...
    })
    export class InjectableClass {

    }

Uma classe declarada como @Injectable é definida como uma classe injetável, ou seja, a partir do momento em que sofre instanciação, seja dentro de um component ou de outra classe injectable, os metadados necessários para criar as dependências da mesma serão gerados. Tais dependências podem ser serviços externos, como a chamada de requisições em uma Api, por exemplo.

O Angular define a injeção de dependências exclusivamente via constructor, ou seja, para que um component possa fazer uso de uma classe Injectable, uma instância dessa classe precisa ser declarada no contructor do component. Observe o exemplo:

    import { Component } from '@angular/core';
    import { InjectableClass } from '...';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
    })
    export class AppComponent {

      constructor(private injectableClass: InjectableClass) {

      }
    }

O Typescript ainda disponibiliza os modificadores de acesso <i>private</i> e o <i>public</i>. Uma Injectable Class declarada como private define que a propriedade a qual ela foi atribuída faz parte da classe ou do component em que ela é declarada, podendo ser chamada através do identificador <i>this.</i>.
