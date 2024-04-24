<h1>@NgModule</h1>

Por ser um framework modular, o Angular possui uma estrutura completa para criar e manutenir módulos. Um módulo é composto por um <b><i>@NgModule()</i></b> decorator, que define a classe imediatamente abaixo como um Module, e cuja função é conter todos os components, directives, pipes e providers da aplicação. A seguir temos um exemplo de declaração de um módulo raiz:

    import { NgModule } from '@angular/core';


    @NgModule({

    declarations:[Component1, Component2],

    imports: [Module1, Module2],

    exports: [MyModule],

    providers: [Service1, Service2],

    bootstrap: [AppComponent]})

    class MyModule { }

No my-app project é possível ter acesso ao módulo raiz, que é criado seguindo o modelo de estrutura do Angular modular. A seguir há uma definição básica para os metadados que compõem o módulo raiz:

- declarations: Lista de todos os components, directives e pipes que serão utilizados no módulo raiz.
- imports: Lista de outros módulos, os quais serão utilizados em algum component ou no próprio módulo.
- exports: O conjunto de components, directives e pipes declarados neste NgModule que podem ser usados ​​no módelo de qualquer component que faça parte de um NgModule que importe este NgModule.
- providers: Lista de serviços disponíveis para todos os components declarados no módulo.
- bootstrap: Indica o component que será instanciado quando a aplicação iniciar o run.
