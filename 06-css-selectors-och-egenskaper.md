# CSS selectors & properties

Selectors och properties används tillsammans för att styla HTML element, som exempelvis bakgrundsfärger, storlekar, text och mer.

## Properties (egenskaper)

Egenskaper är saker man kan sätta på element för att ändra deras utseende och beteende. Om du exempelvis vill byta färg på en text så kan du använda `color` egenskapen. Eller om du vill ändra storleken på ett element så kan du använda `width` och `height`. Properties kan inte användas utan selectors, men säg att du har en knapp som du vill göra röd. Du kan då skriva följande:

```html
<style>
  /* Detta är en selector, mer information om det i kommande sektioner */
  button {
    /* Applicera röd färg på bakgrunden */
    background-color: red;
  }
</style>

<button>A red button</button>
```

Det som bestämmer vilka element som får vilka egenskaper är selectors. Se separat dokument för at lista på vanliga CSS egenskaper.

### Enheter

De flesta egenskaper kan bara ha värden av vissa enheter. Exempelvis så måste `background-color` bestå av en färg och inte en storlek. Storlek är något som bland annat `width` egenskapen vill ha.

Att veta vilka egenskaper som kräver vilka enheter är något som man lär sig över tid, och man kan självklart titta på dokumentationen för att lära sig också. Det viktiga är vilken enhet man skall använda inom samma egenskap, och egentligen så är det mest när det kommer till storlekar.

Det finns flera enheter som du kan använda för exempelvis `width` egenskapen: px, %, vw, vh, rem, em, in och fler. Dem vanligaste som används är: px, % och rem.

#### px enheten

Enheten px står för pixel och bestämmer hur stort, i pixlar, något ska vara. Om du exempelvis sätter `width: 50px` på ett element så blir det elementet 50 pixlar brett.

Enheten px är bra att använda om du vill nå en specifik storlek på något. Den är dock inte så bra då den inte skalar bra, och är därför inte responsivt. Av denna anledning så är det oftast bättre att använda rem.

#### % enheten

Enheten % betyder procent, och den bestämmer hur stort, procentuellt relativt till föräldern, något ska vara. Om du exempelvis sätter `width: 50%` på ett element och föräldern är `500px` bred så blir elementet `250px` brett.

Enheten % är bra att använda om du vill skala något. Storleken har alltid samma proportion oavsett hur webbläsarens fönster ser ut. Om du har en stor skärm så får du samma proportion som med en liten skärm. Det är dock viktigt att förstå att själva storleken skiljer dock, det är bara proportionen som ändras. På grund av detta så kan beteendet av ett element när det kommer till storlek se konstigt ut, om man exempelvis ändrar storleken på webbläsarens fönster, och därför rekommenderas det att använda rem i de flesta fall.

#### rem enheten

Enheten rem står för root element och bestämmer hur stort, procentuellt relativt till root elementet (html elementet) något skall vara. Root elementet bestäms av webbläsarens inställningar. Detta innebär att storleket alltid är anpassad efter användarens preferenser.

rem är i de flesta fall den bästa enheten att använda.

## Selectors

Selectors bestämmer vilka HTML element som får vilka egenskaper. Det finns olika typer av selectors och i denna sektion visas `type`, `id` och `class` selectors. Se "Avancerade selectors" längre ned för kort information om några andra, mer avancerade, selectors.

### Type selectors

Type selectors applicerar egenskaper på alla element av en viss (tag-)typ:

```css
div {
  color: red;
}

span {
  background: blue;
}

button {
  border: 1px solid green;
}
```

Type selectors av sig själva är inte så användbara, men de brukar kombineras med andra [avancerade selectors](./css-other-selectors.md).

### Id selectors

Id selectors applicerar egenskaper på alla element som har ett visst id (se [attributer](./html-attributes.md)).

```css
#main-card {
  color: red;
}

#main-title {
  background: blue;
}

#sidebar {
  border: 1px solid green;
}
```

Idn är till för att identifiera specifika element. Det får endast finnas ett element med ett visst id i samma kod.

### Class selectors

Class selectors applicerar egenskaper på alla element som har en viss klass (se [attributer](./html-attributes.md)).

```css
.card {
  color: red;
}

.title {
  background: blue;
}

.item {
  border: 1px solid green;
}
```

Klasser är till för att identifiera grupper med element. Flera element kan ha samma klass. Om du exempelvis har en sida med en massa knappar som skall vara röda, men inte alla, så kan du lägga på en klass "red-button" och applicera egenskaper på den:

```css
.red-button {
  background: red;
  border: 1px solid red;
}
```

Knapparna som inte skall vara röda får inte klassen.

## Avancerade selectors

Utöver `type`, `class` och `id` selectors (se [selectors](./css-selectors.md)) så finns det även `attribute`, `pseudoclass`, `relative`, `pseudoelement` och några fler selectors. Detta dokument går igenom dem lite kort. Se [länk](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors) för mer information.

### Attribute selectors

En attribute selector väljer element baserat på deras attributer. Följande kod, som ett exempel, skulle applicera bakgrunden på alla element som har en `type` attribute, oavsett värde:

```css
[type] {
  background: red;
}
```

Du kan även vara mer specifik:

```css
[type="checkbox"] {
  background: red;
}
```

### Pseudoclass selectors

En pseudoclass är information kan nås genom CSS men som inte finns i HTML. Det finns många inbyggda pseudoclasses, se [länk](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) för en lista på dem.

Pseudoclass selectors kombineras med vanliga selectors för att nå speciella delar av element, som följande:

```css
div:hover {
  background: red;
}
```

... med koden ovan blir varje div som hamnar under muspekaren röd.

### Relative selectors

En relativ (eller "combinator") selector är en selector som kan välja element relativt till andra element, och det finns flera olika typer av dem. Se [länk](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#combinators) för en lista på dem.

### Pseudoelement selectors

Likt pseudoclasses så väljer pseudoelement selectors speciella delar av element. Se [länk](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) för en lista på dem.

Med pseudoelement selectors kan du exempelvis välja den första bokstaven i en text (i ett element), vilket kan se ut som följande:

```css
div::first-letter {
  background: red;
}
```
