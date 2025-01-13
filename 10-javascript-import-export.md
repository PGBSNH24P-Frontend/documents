# Moduler, export och import

En modul är en fil i JavaScript. Man kan dela upp projekt i flera filer/moduler för att organisera dem. Ta följande situation som exempel för att förklara modules.

Du har följande kod med en massa array hjälp-funktioner och även en massa klasser som inte har något med arrayer att göra:

```javascript
function isInArray(array, value) {
  // ...
}

function countOccurrances(array, value) {
  // ...
}

function findMax(array) {
  // ...
}

function findMin(array) {
  // ...
}

function findMin(array) {
  // ...
}

class Post {
  // ...
}

class User {
  // ...
}

class Comment {
  // ...
}
```

Du borde därför dela upp koden i två filer istället. Den nya filen kan innehålla array funktionerna och kan namnges `array-utils.js`. För att göra det, länka till den i HTML först:

```html
<html>
  <head>
    ...
  </head>
  <body>
    ...
    <script src="array-utils.js" type="module"></script>
    <script src="main.js"></script>
  </body>
</html>
```

_Notera: moduler måste ha en `type="module"` attribut_

Sedan, lägg in alla funktioner i den filen. För att kunna komma åt funktionerna i andra filer/moduler exporteras dem. Det kan göras genom att skriva `export` framför funktionerna, vilket även fungerar på globala variabler.

```javascript
// array-utils.js
export function isInArray(array, value) {
  // ...
}

export function countOccurrances(array, value) {
  // ...
}

export function findMax(array) {
  // ...
}

export function findMin(array) {
  // ...
}

export function findMin(array) {
  // ...
}
```

När alla funktioner är exporterade kan de användas i andra filer genom att använda `import`:

```javascript
// main.js

import { findMin, isInArray } from "./array-utils.js";

isInArray([1, 2, 3], 3);

class Post {
  // ...
}

class User {
  // ...
}

class Comment {
  // ...
}
```

Tänk på att saker som inte exporteras inte kan användas i andra filer.
