# Introduktion till CSS

Webbsidor är skapade från tre komponenter: struktur, styling och funktionalitet. Styling är komponenten som bestämmer hur en webbsida ska se ut. Man kan jämföra det med skinnet på kroppen, och möjligtvis kläder (medans kroppen också har interna organ som representerar JavaScript, och skelettet som representerar HTML). Om du exempelvis har en knapp eller text på en webbsida kan du med styling bestämma vilken färg de skall vara och vilken font de ska ha.

CSS är språket som används för att styla webbsidor. Genom CSS kod kan du bestämma färger, storlekar, fonts, layouts, animationer och mycket mer.

Ett exempel på hur CSS kan se ut är:

```css
.card {
  background: red;
  color: blue;
  width: 4.2rem;
}
```

Det finns två centrala koncept inom CSS:

1. Selectors
2. Properties (egenskaper)

Dessa beskrivs i ett annat dokument. Tillhörande CSS finns även ett till viktigt koncept: layouting (flexbox & grid). Det beskrivs också i ett annat dokument.

För att lägga till CSS på en HTML sida används `style` element:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            max-width: 600px;
            padding: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        h1 {
            color: #2c3e50;
        }
        p {
            line-height: 1.6;
            color: #34495e;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Welcome to My Page</h1>
        <p>This is a simple example of an HTML document with some basic styling.</p>
        <p>The styles are defined in the style tag in the head section.</p>
    </div>
</body>
</html>
```

Man kan även länka till separata filer, vilket är bra för att hålla koden ren:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Example</title>
    <!-- Länka separat css fil -->
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Welcome to My Page</h1>
        <p>This is a simple example of an HTML document with some basic styling.</p>
        <p>The styles are now in a separate CSS file.</p>
    </div>
</body>
</html>
```

```css
/* styles.css */
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}

.container {
  max-width: 600px;
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

h1 {
  color: #2c3e50;
}

p {
  line-height: 1.6;
  color: #34495e;
}
```

## Kommentarer

Kommentarer i CSS skrivs med `/* */`:

```css
/* Detta är en kommentar */

/* 
Snesträck + stjärna öppnar kommentaren
och stjärna + sneträck stänger kommentaren
*/
```
