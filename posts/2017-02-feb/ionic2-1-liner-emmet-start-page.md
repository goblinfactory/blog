# Ionic2 1 liner emmet start page

`VSCode` [supports `Emmet` natively out of the box](http://docs.emmet.io/), so, just for fun, how far can emmit really go? here's a few (`1 for now`) Ionic2 emmets. 

At the very least it's a fun exercise to practice your emmet. After writing a few difficult deeply nested pages, the simpler stuff, especially tables and lists with demo data becomes much easier.

```
ion-header>ion-navbar>button[ion-button][menuToggle]>ion-icon[name=menu]^ion-title{ApName}^ion-toolbar[color=secondary]>ion-title{PgName}
```

**produces**

```html
<ion-header>
  <ion-navbar>
    <button ion-button="" menuToggle="">
      <ion-icon name="menu"></ion-icon></button>
    <ion-title>ApName</ion-title>
  </ion-navbar>
  <ion-toolbar color="secondary">
    <ion-title>PgName</ion-title>
  </ion-toolbar>
</ion-header>
```

**which `almost` gives you everything for this basic starter Ionic2 page**

I cut the emmet slightly short in order for it to fit in a tweet. 

![basic starter Ionic2 page generated using emmet](img/emmet-ionic.png)

> The emmet for a whole page is this

```Emmet
(ion-header>ion-navbar>button[ion-button][menuToggle]>ion-icon[name=menu]^ion-title{ApName}^ion-toolbar[color=secondary]>ion-title{PgName})+ion-content[padding]{Hello my teams}
```

> and produces

```html
<ion-header>
  <ion-navbar>
    <button ion-button="" menuToggle="">
      <ion-icon name="menu"></ion-icon></button>
    <ion-title>ApName</ion-title>
  </ion-navbar>
  <ion-toolbar color="secondary">
    <ion-title>PgName</ion-title>
  </ion-toolbar>
</ion-header>

<ion-content padding>
    Hello my-teams
</ion-content>

```



### References

* http://docs.emmet.io/cheat-sheet/

### A better way to display an emmet snippets?

```
ion-header>
    ion-navbar>
        button[ion-button][menuToggle]>
            ion-icon[name=menu]
        ^ion-title{ApName}
    ^ion-toolbar[color=secondary]>
        ion-title{PgName}
```
