# My Ionic2 files quick reference

![Ionic2 files quick reference](img/ionic-files.png)

## `index.html`

1. Generic entry point contains `<ion-ap></ion-app>`
1. loads all the compiled (ts) files that make up your spa app. `build/main.js`

## `/app/app.module.ts`

1. this file loads everything : via declares, imports and bootstraps of the `@NgModule`
1. specify your root **component** that will contain your navigation and any custom app start code

## `/app/app.component.ts` and (`app.component.html`)

1. hides the splash screen and starts everything by starting your menu
1. holds the navigation definitions e.g. `<ion-nav ... `

## `/app/pages/hello.component.ts` and (`hello.component.html`)

1. your components, that are being loaded by the menu navigation

## references

* http://ionicframework.com/docs/v2/intro/tutorial/project-structure/

### home

[back to my experimental blog](../../README.md)