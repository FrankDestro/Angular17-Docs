![image](https://github.com/FrankDestro/Curso-Angular-17/assets/93776452/c0f490ab-b736-4347-8ac9-a2513cc3a0c1) 

# Angular-17 

## Ferramentas e versões 
* Angular CLI 18.0.7
* NodeJS 20.12.2
* TypeScript 5.4.2
* linux x64 Fedora 40 KDE Plasma

## Criação de um projeto Angular 

Gerar um novo projeto Angular - Ao criar um projeto o primeiro component que será executado é: app.component.html

```css
ng new project --no-standalone 
```
* --no-standalone (criar o projeto com o arquivo app.modules.ts) para compatibildiades com projeto Angular < 16

## Estrutura de um componente 

Gerar um novo componente

```css
ng generate component componente
```

- card.component.scss -> estilização (css)
- card.component.html -> html 
- card.component.spec.ts -> testes unitários
- card.component.ts -> classe do componente Javascript
- src/app/app.module.ts -> declarou na classe app.modules.ts

```css
Angular17/ ng generate component card
CREATE src/app/card/card.component.scss (0 bytes)
CREATE src/app/card/card.component.html (19 bytes)
CREATE src/app/card/card.component.spec.ts (583 bytes)
CREATE src/app/card/card.component.ts (192 bytes)
UPDATE src/app/app.module.ts (467 bytes)
```

![image](https://github.com/FrankDestro/Curso-Angular-17/assets/93776452/c8b75ee0-b490-4b59-b6a0-cd0f68999472)

## Classes Angular 

### @Component
Define um componente Angular, especificando seu template, estilos, e outras propriedades.

```js
import { Component } from '@angular/core';

@Component({
  selector: 'app-card',
  templateUrl: './card.component.html',
  styleUrl: './card.component.scss'
})
export class CardComponent {

}
```

* selector - identifica o componente HTML podendo referenciar em outro componente.
```js
<app-card/>
```
* templateUrl  - Define o layout e a estrutura HTML que o componente irá renderizar
```js
<div>
  <h1>{{ title }}</h1>
  <p>Welcome to {{ title }}!</p>
</div>
```
* styleUrl - caminho para o css de estilização do componente. 
```js
h1 {
  color: blue;
}
p {
  font-size: 20px;
}
```

### @NgModule 
É usado para definir um módulo em Angular. Um módulo é um contêiner que agrupa componentes, diretivas, pipes e serviços relacionados, facilitando a organização e a manutenção da aplicação. Vamos analisar cada uma das propriedades e o que elas fazem no exemplo fornecido:

Gerar um novo módulo 

```css
ng generate module cards
```

```js 
@NgModule({
  declarations: [
    AppComponent,
    CardComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

### Utilizando componente de um módulo em outro módulo. 

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/c70548b7-7234-4665-8e77-b6292a1372f0)

### Interpolação em Angular 

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/37d8015e-b618-48f4-816f-31bed23fa162)

### Angular Material 

Angular Material é uma biblioteca de componentes UI desenvolvida pelo Angular Team da Google que implementa os princípios de Material Design. Ela fornece uma série de componentes prontos para uso, como botões, inputs, dialog boxes, cards, e muitos outros, todos seguindo as diretrizes de design do Material Design

Instalação do Angular/Material 
```css
ng add @angular/material
```

processo de instalação :

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/73ad346e-df77-4714-bed8-cf0e1865930a)

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/9a2aaaff-f89b-4c50-8de1-326c55776c63)

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/5ae515df-57ef-498d-b828-1f8306305915)

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/e95b8bc4-c030-40fb-97e3-fde4ef447af2)

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/1421c454-6e53-4dd4-b8db-def0679a5fc7)

### Utilização do Angular/Material 

1 - passo 

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/48303c2f-4527-4775-ba97-dfc839a5a41c)

2 - passo 

#### Adicionar o theme nas configurações globais no styles.scss

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/a31f98b1-c034-4041-b5d6-fc856e60ad6e)







