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

> and produces the html below, which the full template html for the screenshot shown. 

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

### heres the emmet snippet broken down

```
(ion-header>
    ion-navbar>
        button[ion-button][menuToggle]>
            ion-icon[name=menu]
        ^ion-title{ApName}
    ^ion-toolbar[color=secondary]>
        ion-title{PgName})
 +ion-content[padding]{Hello my-teams}
```

* the ` > ` indicates what follows is a child, lines are indented for display purposes.
* the ` ^ ` indicates that what follows 'pops' back up a level, which is why I've shown it dedented above. 

### References

* http://docs.emmet.io/cheat-sheet/
* http://docs.emmet.io/

[back to my experimental blog](../../README.md)