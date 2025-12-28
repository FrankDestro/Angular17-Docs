![image](https://github.com/FrankDestro/Curso-Angular-17/assets/93776452/c0f490ab-b736-4347-8ac9-a2513cc3a0c1) 

# Angular-19

## Ferramentas e versões 
* Angular CLI 19.2.19
* NodeJS 20.12.2
* TypeScript 5.4.2
* Zorin OS 18

## Instalação Angular CLI globalmente 
### Via npm 

```css
npm install -g @angular/cli 
npm install -g @angular/cli@19
```

## Instalação Angular CLI não global (temporário)
### Via npx 

```css
npx @angular/cli@19 new project --ssr=false --style=scss
```

## Criação de um projeto Angular 

Gerar um novo projeto Angular - Ao criar um projeto o primeiro component que será executado é: app.component.html

```css
ng new project --no-standalone --ssr=false --style=scss
```
* --no-standalone (criar o projeto com o arquivo app.modules.ts) para compatibildiades com projeto Angular < 16

Versões mais novas > 16 
```css
ng new project --ssr=false --style=scss
```

# 🧠 Seção 4 - Fundamentos Angular - Componentes e Estilização.

- Conceitos de componente
- Como criar componentes
- Problemas na duplicação de componentes
- Como criar componentes filhos
- Como referenciar componentes de outros módulos (externos) → agora via imports
- Interpolaçãohttps://github.com/FrankDestro/Angular-19/edit/main/README.md
- Estratégias de estilização
- Inline Template e Inline CSS
- :host
- ::ng-deep
- View Encapsulation (None, Emulated, ShadowDOM)

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

### @NgModule (Obs. Versões superior a 16 não tem mais o @NgModule)
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

### View Encapsulation

```css
@Component({
  selector: 'app-card',
  templateUrl: './card.component.html',
  styleUrl: './card.component.scss',
  encapsulation : ViewEncapsulation.ShadowDom
})

```

Encapsulated: Em Angular, o encapsulamento refere-se ao escopo de estilos CSS aplicados a componentes. Por padrão, os estilos CSS de um componente Angular são encapsulados, o que significa que eles não afetam outros componentes fora do escopo, utilizando o ‘ViewEncapsulation’ no componente. Os tipos são:
1.	Emulated: Em angular, o encapsulamento de estilos é frequentemente emulado usando um mecanismo interno para garantir que os estilos de um componente sejam aplicados apenas ao seu próprio escopo, sem vazar para outros componentes.
2.	ShadowDom: é um tipo de encapsulamento mais avançado de estilos e comportamentos de componentes, fazendo com que os estilos do componente não vazem para fora e que o componente não pegue estilos externos, ele fica desabilitado até para estilos globais. 
3.	None: Em Angular, "none" pode ser usado para indicar que nenhum encapsulamento de estilo deve ser aplicado a um componente específico, o que significa que os estilos definidos para esse componente podem afetar globalmente a aplicação.
Esses termos são frequentemente usados para descrever como os estilos são aplicados e encapsulados dentro da arquitetura de componentes do Angular.

## Binding, Diretivas, Templates, Decorators

### Atributos vs propriedades de um Elemento HTML.

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/0349a52d-a0dc-4373-93dd-edb33480ba68)

### Tipos de Binding no Angular

- `{{ }}` → **Interpolação** (TS → HTML)
- `[ ]` → **Property Binding**
- `( )` → **Event Binding**
- `[()]` → **Two-way Binding**g

### Interpolação em Angular (um tipo de binding no Angular)

![image](https://github.com/FrankDestro/Angular17-Docs/assets/93776452/37d8015e-b618-48f4-816f-31bed23fa162)

### Properties Binding 

Property binding é usado para passar dados de um componente para uma propriedade de um elemento HTML ou outro componente Angular. Ele permite que você ligue uma propriedade de um componente pai a uma propriedade de um componente filho ou a uma propriedade HTML nativa.

![image](https://github.com/user-attachments/assets/57ceb561-f2a3-453b-913c-2ee9ed9c5894)


### Event Binding 

Event binding é usado para capturar eventos disparados por elementos HTML ou outros componentes Angular e chamar métodos no componente. Ele permite que você reaja a eventos como cliques, digitação de texto, movimentos do mouse, entre outros.

![image](https://github.com/user-attachments/assets/ac7a2648-6948-44a1-a36b-93b1a1d45252)
