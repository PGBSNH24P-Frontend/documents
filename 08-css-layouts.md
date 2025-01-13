# CSS layouts

Att skapa en layout betyder att du bestämmer vilka platser komponenter (knappar, fält, paragrafer m.m) ska läggas på. När du exempelvis designar en webbsida så måste du bestämma var huvudinnehållet ska ligga och var alla länkar (navbar) ska ligga. I HTML & CSS så finns det många sätt att hantera detta på, men det är främst två sätt som står ut: grids och flexbox. Både grids och flexbox används för att skapa layouts men de är bra på olika saker. Flexbox är en "one-dimensional" metod medans grids är en "two-dimensional" metod. Vad det betyder beskrivs mer nedanför, men det är viktigt att veta att det du kan göra med flexbox kan du också göra med grids, och tvärtom. Den enda skillnaden mellan dem är hur smidigt det är att göra saker.

## Flexbox

Flexbox är en "one-dimensional" metod, vilket betyder att du styr betéendet på element i en riktning (X axel eller Y axel). Man kan styra två dimensioner samtidigt om man använder flexbox flera gånger, men i dessa fall passar grids oftast bättre.

Det finns många egenskaper som ingår i flexbox modulen:

- display: flex
- order
- flex-direction
- flex-wrap
- flex-grow
- flex-shrink
- flex-basis
- flex-flow
- justify-content
- align-self
- flex
- align-items
- align-content
- gap

I de flesta fall används bara några av dessa, och det är också oftas samma egenskaper som används om och om igen. Exempelvis så används `flex-shrink` sällan medans `justify-content` används mycket.

Flexbox fungerar genom "containers". En container kan vara ett vanligt element som ska innehålla flera andra element, som du vill styra. En knapp är ett dåligt val för en container eftersom de oftast bara innehåller text, medans en div kan vara väldigt passande. Det kan finnas flera containers om man vill använda flexbox flera gånger. När ett element har fått en `display: flex` så blir det en "flexbox container" och alla barn börjar följa flexbox regler. Alla andra egenskaper (utöver `display`) används för att bestämma hur barnen ska beté sig. Om du exempelvis har följande HTML:

```html
<div id="my-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

... så kommer alla element lägga sig vertikalt. Men om du sätter på `flex-direction: column` som följande:

```css
#my-container {
  display: flex;
  flex-direction: column;
}
```

... så kommer alla element att byta riktning och lägga sig horisontellt.

Se [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) för beskrivningar på alla egenskaper och exempel.

## Grid

Grid är en "two-dimensional" metod, vilket betyder att du kan styra hur element ska beté sig i två riktningar (X- och Y axel samtidigt). Grid passar väldigt bra för att strukturera webbsido-layouts. Som exempel, den som utvecklar en webbsida behöver bestämma var på sidan huvudinnehållet ska ligga, var sidpanelen ska ligga och var alla länkar ska ligga. Dessa komponenter spannar oftast över flera axlar (sidpanelen och huvudinnehåller ligger bredvid varandra och länkarna finns längst upp exempelvis) och därför så passar grid bra. Med grid kan du enkelt placera ut komponenter på olika positioner.

Det finns många egenskaper som ingår i grid modulen:

- display: grid
- gap
- grid-column-start
- grid-column-end
- grid-row-start
- grid-row-end
- grid-template-rows
- grid-template-columns
- grid-area
- grid-template-areas
- justify-self
- align-self
- column-gap
- row-gap
- place-self
- justify-items
- align-items
- place-items
- justify-content
- align-content
- place-content
- grid-auto-flow
- grid-auto-rows
- grid-auto-columns

Det finns även några fler egenskaper som sammansätter andra egenskaper.

Precis som med flexbox så fungerar grid genom "containers". När du sätter `display: grid` på ett element så blir det en "grid container" och alla barn börjar följa grid regler.

Se [A Complete Guide to CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) för beskrivningar på alla egenskaper och exempel.
