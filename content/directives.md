<h1>@Directives</h1>

Directives, ou diretivas, são classes que atribuem comportamento extra a elementos do template de um component, com as quais é possível gerenciar formulários, listas, styles, e a interface em si. A capacidade de criação de estruturas lógicas mediante a inclusão de diretivas no template de um component dá ao desenvolvedor uma capacidade imensa de manipulação do Document Object Model, criando assim uma interface muito mais interativa. As diretivas disponibilizadas pelo Angular são:

<h3>*ngFor</h3>

Um for é uma declaração de controle de fluxo que executa uma interação de acordo com os parâmetros definidos na sua estrutura, normalmente associada a quantidade de elementos de uma unidade de armazenamento, como uma variável ou vetor. O \*ngFor possui o mesmo conceito, e para entendê-lo melhor, imagine o seguinte cenário:

    import { Component } from '@angular/core';


    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
    })

    export class AppComponent {

      movies: string[] = ['Good Fellas', 'The Irishman', 'Taxi Driver'];

      constructor() {}

    }

Temos um component e nele a declaração da propriedade <i>movies</i>. A ela é data a definição de array, e com isso, a ela são atribuídos três índices. Em seguita, na app.component.html, temos:

    <ul>
      <li *ngFor="let movie of movies">
        {{ movie }}
      </li>
    </ul>

Ao declarar um \*ngFor, basicamente está sendo dito que o Angular deve interar o atributo movies, e a cada interação, o valor do elemento atual(índice) deve ser atribuído a variável <i>let movie</i>. Também está sendo dito que a tag li deve ser replicada a cada interação. Além disso, há uma interpolação do valor atribuído a let movie, ou seja, para cada interação haverá um li com o valor encontrado no índice. Resultado:

    *Good Fellas
    *The Irishman
    *Taxi Driver

<h3>*ngIf</h3>

A diretiva \*ngIf possui o mesmo comportamento de uma estrutura if-else, onde é possível declarar um ou mais parâmetros condicionais, os quais definem o retorno da informação que atender a condição imposta, ou o oposto. Para entendê-lo melhor, imagine o seguinte cenário:

    import { Component } from '@angular/core';


    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
    })

    export class AppComponent {

      songs: string[] = [];

      constructor() {}

    }

Um array to tipo string é declarado como vazio na classe AppComponent. Essa unidade de armazenamento será o elemento base da estrutura condicional que iremos criar com o \*ngIf. Em seguida temos:

    <div *ngIf="songs.length > 0">
     Lista de músicas
    </div>

    <div *ngIf="songs.length == 0">
     A lista de músicas está vazia
    </div>


    //browser:

     A lista de músicas está vazia

Ao lançar a aplicação, temos resultado o definido na condição atendida, esta sendo o length do array songs == 0. Para um resultado diferente modifique o atributo songs incluindo alguns nomes de músicas, com por exemplo:

    songs: string[] = ['Children of the Grave', 'Panaroid', 'Immigrant Song'];

Para melhorar um pouco o resultado, modifique o arquivo app.component.html incluíndo a diretiva \*ngFor da seguinte forma:

    <div *ngIf="songs.length > 0">
    Lista de músicas
     <ul>
       <li *ngFor="let song of songs">
         {{ song }}
       </li>
     </ul>
    </div>

    <div *ngIf="songs.length == 0">
     A lista de músicas está vazia
    </div>

A condição atendida foi a que definia um length maior que zero para o array songs, resultado em uma alteração do template.

    //browser:

    Lista de músicas
    Children of the Grave
    Panaroid
    Immigrant Song

...
