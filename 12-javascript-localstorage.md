# Local Storage

Local storage är en modul som är inbyggd i JavaScript. Den kan användas för att spara information som lagras över tid. Om du har en vanlig variabel försvinner när du stänger ned webbsidan, med med local storage kan du spara data som finns kvar även efter att du stänger ned webbsidan.

Local storage tar endast emot strängar, och JSON brukar då användas som format.

Använd:

```javascript
// Använd JSON.stringify för att omvandla vilket värde som helst till JSON format.
let json = JSON.stringify(value);

// Om du vill omvandla en JSON-sträng tillbaka till ett JavaScript värde, använd JSON.parse.
let value = JSON.parse(json);
```

## API

Spara saker till local storage med:

```javascript
localStorage.setItem("nyckel", value);
```

... där `"nyckel"` är ett valfritt namn och `value` är ett JSON värde (tekniskt sätt en sträng, men JSON brukar användas).

Hämta saker från local storage med:

```javascript
let json = localStorage.getItem("nyckel");
```

... där `"nyckel"` är ett valfritt namn. Det måste vara samma nyckel som du sparade med.

## Övrigt

Användare kan fritt se, ändra och radera deras egen local storage data. Tänk på det när du utvecklar webbsidor. Spara aldrig viktig eller privat information i local storage.
