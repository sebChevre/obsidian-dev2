---
created: 2025-11-18 - 20:42
tags:
  - md
---
## Fenêtre de codes/commandes

#### bash
Syntaxe:
````plaintext
```bash
curl -X POST -is "http://localhost:4242/create-checkout-session" -d ""
```
````
Résultat:
```bash
curl -X POST -is "http://localhost:4242/create-checkout-session" -d ""
```

#### javascript
Syntaxe:
````plaintext
```JavaScript=
function foo(bar) {
  var a = 42,
    b = "Prism";
  return a + bar(b);
}
```
````
Résultat:
```javaScript
function foo(bar) {
  var a = 42,
    b = "Prism";
  return a + bar(b);
}
```

#### HTML
Syntaxe:
````plaintext
```html
<html>
  <head>
    <title>Buy cool new product</title>
  </head>
  <body>
    <!-- Use action="/create-checkout-session.php" if your server is PHP based. -->
    <form action="/create-checkout-session" method="POST">
      <button type="submit">Checkout</button>
    </form>
  </body>
</html>
```
````

Résultat:
```html
<html>
  <head>
    <title>Buy cool new product</title>
  </head>
  <body>
    <!-- Use action="/create-checkout-session.php" if your server is PHP based. -->
    <form action="/create-checkout-session" method="POST">
      <button type="submit">Checkout</button>
    </form>
  </body>
</html>
```

#### Structure hiérarchique
Syntaxe:
````plaintext
```treeview
├── fonts/
├── images/
├── js/
│   ├── vendor/
│   ├── app.js
│   └── index.js
├── lambda/
└── scss/
    ├── common/
    ├── components/
    ├── layouts/
    ├── vendor/
    └── app.scss
```
````
Résultat:
```treeview
├── fonts/
├── images/
├── js/
│   ├── vendor/
│   ├── app.js
│   └── index.js
├── lambda/
└── scss/
    ├── common/
    ├── components/
    ├── layouts/
    ├── vendor/
    └── app.scss
```

## Alertes
#### Note
Syntaxe:
````plaintext
> [!NOTE]
> Useful information that users should know, even when skimming content.
````
Résultat:
> [!NOTE]
> Useful information that users should know, even when skimming content.

#### Tip
Syntaxe:
```?plaintext
> [!TIP]
> Helpful advice for doing things better or more easily.
````
Résultat:

> [!TIP]
> Helpful advice for doing things better or more easily.

Egalement avec `!IMPORTANT`, `!WARNING`, `!CAUTION`.

## Note

Syntaxe:
```plaintext
> **Note**\
> This is a note
```

Résultat:
> **Note**  
> This is a note


## Icônes

⚠️ warning

##### Liens sur site icône md
- https://gist.github.com/rxaviers/7360908
- https://www.flaticon.com/free-icons/markdown

## SVG

##### Liens site icône svg
- https://iconsear.ch/search.html
- https://www.svgrepo.com/


