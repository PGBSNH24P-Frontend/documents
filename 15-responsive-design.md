# Responsiv design

Responsiv design handlar om att skapa webbsidor som fungerar bra oavsett skärmstorlek. Du kanske har märkt någon gång att en webbsida ser bra ut på en datorskärm, men när du går in på telefonen så blir allting konstigt. Om du har sett det så betyder det att den webbsidan **inte** var responsiv. En responsiv sida är en sida som fungerar, och ser bra ut, på alla skärmstorlekar.

Det finns jätte många olika skärmstorlekar och som utvecklare så bör du se till så att din webbsida fungerar lika bra på alla av dem. I vissa fall dock så behöver du inte anpassa efter specifika storlekar som inte förekommer så ofta. Det brukar vara bra att anpassa efter fyra storlekar (eftersom de täcker det mesta): telefon, platta, laptop och tv. Däremot, om man har en webbsida som inte brukar visas på tv kan man skippa den storleken.

För att en webbsida skall vara responsiv måste den fungera bra på två fronter: funktionalitet och utseende. Alltså, alla funktionella delar skall fungera lika bra på alla skärmstorlekar och alla viktiga komponenter ska synas på alla skärmstorlekar.

Följande är ett exempel på hur en responsiv sida kan se ut:

![Responsiv webbsida](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*8al0RhBlJgA2P0Br_OQHqQ.jpeg&f=1&nofb=1&ipt=d3af991987e55a69ca62776e7ba28d2303b05834322e332d9fbe25076b5dcc1b&ipo=images)

... som du kan se ändras utseendet för att passa till storleken. Layouts är det främsta sättet att hantera responsivitet (när det kommer till utseende, vilket också hjälper till med funktionaliteten).

## Hantering

Det finns många olika sätt att hantera responsivitet på. I detta dokument beskrivs två av dem: layout (med flexbox och grid) och media queries.

### Layout

Media queries, som beskrivs i nästa del, är lite av ett specialiserat sätt att hantera responsiv design. Men i många fall räcker det att välja en layout som fungerar oavsett skärmstorlek, och då behöver du inte göra något speciellt för att göra sidan responsiv. Ta följande exempel:

Föreställ dig att du vill ha följande layout för en större skärm:

![bild](https://i.ibb.co/f4Srj1w/before-layout-rd.png)

... vilket är resultatet av:

```html
<!doctype html>
<html>
  <head>
    <style>
      #container {
        display: flex;
        gap: 5px;
      }

      #container div {
        background: red;
        min-width: 100px;
        min-height: 200px;
      }
    </style>
  </head>

  <body>
    <div id="container">
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
      <div>A</div>
    </div>
  </body>
</html>
```

... detta är inget problem för en större skärm, men om du sätter samma kod på en mindre skärm så blir det konstigt, och de flesta element flyttas ut till höger där de inte syns:

![bild](https://i.ibb.co/DwtGSpN/bad-layout-rd.png)

... men om du gör en enkel ändring och lägger till `flex-wrap` i CSSen:

```css
#container {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

#container div {
  background: red;
  min-width: 100px;
  min-height: 200px;
}
```

... löser problemet sig automatiskt och sidan fungerar lika bra på en stor skärm som på en liten skärm, eftersom man nu kan scrolla ned för att se alla element (scroll visas inte eftersom det är en bild):

![bild](https://i.ibb.co/kX8VNqf/after-rd.png)

Med andra ord, det krävdes ingen speciell lösning för att göra sidan responsiv, och även om det är ett simpelt exempel förekommer liknande saker ganska ofta. Det är bättre att använda denna metod när det går (eftersom det är mycket enklare att förstå och det är också mer effektivt), än att vända sig till media queries.

### Media queries

Media queries handlar om att styra layouts för det mesta, men man kan även göra andra saker. En media query är som en slags selector som kan applicera styling på element när vissa krav uppfylls. Du kan exempelvis sätta styling på element när en skärm har en viss storlek, som i följande exempel:

```css
@media screen and (min-width: 1000px) {
  div {
    background: red;
  }
}
```

... vilket gör alla divar röda om skärmen är minst 1000px bred (vilket de flesta datorskärmar är).

Oftast brukar detta användas på grupper av element eller specifika element, och inte så ofta på "hela" layouts. Det är exempelvis vanligt att gömma (e.g `display: none`) ett visst element (e.g en bild) för en telefon eftersom de inte har så mycket utrymme, medans en datorskärm inte har några problem med att visa en eller flera bilder. Ett annat exempel kan vara att datorskärmar visar hela menyer, medans på telefoner läggs valen ihop till en "hamburger menu" och visas endast om man trycker på knappen.
