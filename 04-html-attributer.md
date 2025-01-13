# HTML attributer

En attribut är en slags inställning som du kan sätta på element. I vissa fall lägger attributer bara till extra information, och i vissa fall styr de funktionalitet, och i vissa fall ändrar de utseende. Syntax för attributer är som följande:

```html
<div attribute1="value1" attribute2="value2"></div>
```

Precis som med tags så finns det inbyggda attributer i HTML som gör olika saker. De mest förekommande är `id` och `class` som används för att identifiera specifika element. Detta är främst användbart i CSS. Sedan finns det andra attributer som ändrar beteendet och utseendet på element. Ta `input` taggen som exempel. Om du skriver:

```html
<input />
```

... så dyker ett vanligt inputfält upp. Men om du lägger till `type` attributen på den med `checkbox` som värde:

```html
<input type="checkbox" />
```

... så kan du göra inputfältet till en checkbox (testa själv för att se resultat) istället.

Varje attribut har ett namn (attributen i sig) och ett värde. Olika attributer tillåter olika värden. `id` och `class` kan ta in vad som helst, men `width` tar endast in `length` enheter exempelvis. Med andra ord så kan du inte skriva:

```html
<!-- Rätt, 100 pixlar -->
<img width="100px" />

<!-- Fel -->
<img width="hello" />
```

Vilka attributer som tar in vilka enheter är något som man lär sig över tid, och mycket information kan hittas i dokumentationen.

## Exempel

Nedan följer några exempel på element som ofta har attributer. Testa dem gärna själv för att se vad som händer. Testa också att lägga till bilder och länka dem (som i första exemplet).

```html
<img src="./my-folder/my-image.png" width="100px" height="50px" />
```

```html
<div class="container"></div>
```

```html
<form>
  <label for="username">Username</label>
  <input placeholder="Type here..." name="username" id="form-username" />
  <label for="password">Password</label>
  <input
    placeholder="Type here..."
    type="password"
    name="password"
    id="form-password"
  />
</form>
```

```html
<span id="card-content"></span>
```
