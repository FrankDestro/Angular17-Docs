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

Gerar um novo componente

```css
ng generate component componente
```

## Estrutura de um componente 
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
