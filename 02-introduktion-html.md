# Introduktion till HTML

Hypertext Markup Language, förkortat 'HTML', är språket som används för att strukturera webbsidor. Med HTML bestämmer du vad som skall finnas på en webbsida (e.g. knappar, navbars, bilder m.m), men inte utseendet eller funktionaliteten (det görs med CSS och JavaScript).

Ett exempel på hur HTML kan se ut är:

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

Det finns tre centrala koncept inom HTML:

1. Taggar (& element)
2. Hierarkier
3. Attributer (beskrivs i separat dokument)

Det är också viktigt att veta hur man kommenterar HTML, och det görs genom speciella taggar (mer info om taggar kommer nedanför):

```html
<!-- Detta är en kommentar -->
<!-- Kommentarer
måste börja med 
vänsterpil, utropstecken och två bindesträck
och avslutas med
två bindesträck och högerpil
-->
```

## Taggar och element

Taggar är byggstenarna för alla webbsidor, för all HTML. Det finns tre typer av taggar och de ser ut såhär syntaxmässigt:

```html
<!-- Start taggar (start tags, opening tags) -->
<!-- De har två pilar med ett namn innanför -->
<tag-name>

<!-- Slut taggar (end tags, closing tags) -->
<!-- De har också ett snesträck i början -->
</tag-name>

<!-- Hel taggar (full tags, single tags) -->
<!-- De har två pilar med ett namn innanför och ett snesträck på slutet -->
<tag-name />
```

Start-taggar och slut-taggar används tillsammans oftast, och hel-taggar förekommer mer sällan. Start-taggar och slut-taggar kombineras för att bilda element:

```html
<!-- Endast en start tag-->
<tag-name>

<!-- Endast en slut tag -->
</tag-name>

<!-- Nu är det ett element: start och slut har kombinerats för att bilda ett element -->
<tag-name></tag-name>

<!-- Hel taggar kan alltid räknas som element också -->
<tag-name />
```

Ett element är alltså två taggar, en start och en slut, som har kombinerats. Syftet med element är att kunna skriva in fler element eller text. Inom element kan flera andra element finnas, och även text. Låt oss introducera några vanliga, inbyggda, taggar först dock, som kan användas i exempel.

Olika taggar gör olika saker, och fungerar på olika sätt. Det finns många inbyggda taggar i HTML, här är några av dem:

- `div` - represenrerar en generisk behållare
- `p` - representerar en paragraf
- `button` - representerar en knapp
- `img` - represenrerar en bild
- `h1` - representerar en huvudtitel

Som exempel, denna paragraf du läser just nu kan byggas med följande HTML:

```html
<p>
Som exempel, denna paragraf du läser just nu kan byggas med följande HTML:
</p>
```

Eller låt säga att du vill ha lite text och en knapp:

```html
<!-- 
Först en div för att hålla alla element.
Detta är användbart när HTML kombineras med CSS.
-->
<div>
  <p>Kolla på den snygga knappen nedanför!</p>
  <button>En snygg knapp</button>
</div>
```

Notera också indenteringen på koden: om ett element ligger innanför ett annat element skall det indenteras ett steg (2 eller 4 spaces).

## Hierarkier

Element som ligger innanför andra element bildar hierarkier. Följande termer brukar användas då:

- barn (child)
- förälder (parent)
- syskon (sibling)

Ta följande exempel:

```html
<!-- Parent till: p, button och den andra div:en -->
<!-- Child till: inget annat element eftersom det är det första elementet -->
<div> 
  <!-- Parent till: ingen -->
  <!-- Child till: div -->
  <p></p> 

  <!-- Parent till: ingen -->
  <!-- Child till: div -->
  <button></button>

  <!-- Parent till: img -->
  <!-- Child till: div -->
  <div>
    <!-- Parent till: ingen -->
    <!-- Child till: div -->
    <img />
  </div>
</div>
```

Hierarier är viktiga att förstå för att kunna strukturera webbsidor korrekt, och även för att kunna styla dem med CSS.

## HTML-, head-, och body-tags

Grunden för alla HTML dokument innehåller HTML-, head- och body-tags:

```html
<!-- Denna markerar början av dokumentet -->
<html>

  <!-- Head innehåller meta information som titeln på sidan, inställningar och annat -->
  <head></head>

  <!-- Body innehåller själva webbsidan: alla taggar och element, paragrafer, bilder, knappar och så vidare -->
  <body></body>

<!-- Slut taggen markerar slutet av dokumentet -->
</html>
```
