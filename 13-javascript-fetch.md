# Fetch API

I fetch API:et ingår en funktion som kan användas för att hämta data från webb API:er. Den tar in två argument: url och options. URL:en bestämmer vilket webb API fetchen kommer att använda. Options bestämmer vilka inställningar meddelandet får. För att förstå options delen så måste man förstå HTTP.

## HTTP och HTTPS

HTTP står för "HyperText Transfer Protocol" och är ett protokoll som används på webben för kommunikation mellan datorer. Varje gång du besöker en webbsida skickas ett HTTP meddelande till en server som svarar med en HTML webbsida. Det finns olika typer av HTTP meddelanden:

- `GET` - Används typiskt sätt för att hämta data
- `POST` - Används typiskt sätt för att ladda upp ny data till servern
- `PUT` - Används typiskt sätt för att uppdatera data på servern
- `DELETE` - Används typiskt sätt för att radera data från servern

Detta bestämmer man genom options i fetch:

```javascript
fetch("url", { method: "POST" });
```

Varje meddelande består även av en kropp som kallas `body`. Kroppen är huvudinnehållet för meddelandet. Om du behöver ladda upp data så använda kroppen för det oftast. Det kan se ut såhär:

```javascript
fetch("url", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(someValue),
});
```

Notera att det också finns med en `headers` egenskap. Den behövs om du skickar med en kropp så att servern förstår vilket format du skickar data i. Det vanligaste är att skicka data som JSON, och då används `Content-Type: application/json` som header.

Slutligen så måste man hantera svaret från meddelandet, vilket man kan göra med `.then`:

```javascript
fetch("url").then(function(response) {
  // Gör något med response objektet.
});

// Ibland får man tillbaka data i svaret och då kan den parsas såhär (om det är JSON):
fetch("url")
  .then(function(response) {
    return response.json();
  })
  .then(function(jsonObject) {
    console.log(jsonObject);
  });
```

## JSON

JSON står för "JavaScript Object Notation" och är ett dataformat som är väldigt likt JavaScript. All JSON är i form av strängar och kan se ut såhär:

```json
{
  "name": "Ironman",
  "age": 4,
  "superpowers": ["Rich", "Suit"]
}
```

Notera att skillnaderna mellan JSON och JavaScript är:

1. Egenskaper i JSON ska omringas av `""` medans JavaScript inte kräver det.
2. Ett JSON objekt är alltid en sträng (oavsett datatyp) medans JavaScript sparar olika datatyper på olika sätt
