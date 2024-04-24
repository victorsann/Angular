<h1>Template</h1>

Todo component possui um template HTML que declara como esse component será renderizado. É possível declarar um template em inline ou usando um path de um arquivo separado, que é algo mais comum. Além disso, o Angular adiciona funcionalidades a sintaxe do HTML que permitem a inserção de valores dinâmicos vindos do component. Com isso, o DOM sofre um update cada vez que houver uma atualização no state do component. Para entender melhor o conceito, faça as seguintes modificações no my-app criado anteriormente:

No arquivo <i>app.component.ts</i> faça a seguinte alteração:

    import { Component } from '@angular/core';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
    })
    export class AppComponent {
      message = 'Hello, World!';
    }

Remova todo o HTML do arquivo <i>app.component.html</i> e inclua a tag a seguir:

    <p>{{ message }}</p>

O uso das chavez duplas {{ }} é chamado de interpolação, que é um recurso utilizado desde o Angular 1, cuja função é definir que o valor atribuído a uma variável será mostrado na tag em que for declarado. Com isso, ao rodar a aplicação temos a mensagem contida no atributo <i>message</i> em tela. Caso essa mensagem seja modificada, a aplicação irá fazer um rerender da tela, atualizando a mensagem.
