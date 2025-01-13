# Document Object Model (DOM)

DOM står för "Document Object Model" och är ett API som är till för att manipulera HTML genom JavaScript. DOM:en representerar hela webbsidan som ett träd av objekt, där varje HTML-element är en nod i trädet. Detta gör att man kan modifiera webbsidans struktur, innehåll och design dynamiskt.

För att komma åt API:et används den globala variabeln `document`, som representerar hela HTML-dokumentet.

## Grundläggande DOM-manipulation

### Skapa nya element

För att skapa ett nytt element används `createElement`:

```javascript
// Skapa ett nytt div-element
let divElement = document.createElement("div");

// Skapa ett nytt paragraph-element
let pElement = document.createElement("p");

// Skapa en ny knapp
let buttonElement = document.createElement("button");
```

### Lägga till element på sidan

Nyskapade element måste läggas till i DOM:en för att kunna synas. Detta kan göras på flera sätt:

```javascript
// Lägg till i slutet av ett element
parentElement.append(newElement);

// Lägg till i början av ett element
parentElement.prepend(newElement);

// Lägg till före ett specifikt element
existingElement.before(newElement);

// Lägg till efter ett specifikt element
existingElement.after(newElement);
```

### Hitta existerande element

Det finns flera metoder för att hitta element på sidan:

```javascript
// Hitta ett element med specifikt ID
let element = document.getElementById("some-id");

// Hitta element med en specifik klass (returnerar en HTMLCollection vilket är en slags array med element)
let elements = document.getElementsByClassName("some-class");

// Hitta element av en specifik typ (returnerar en HTMLCollection)
let divs = document.getElementsByTagName("div");

// Använd CSS-selektorer (returnerar första matchande element)
let element = document.querySelector(".class-name");

// Använd CSS-selektorer (returnerar alla matchande element som en NodeList)
let elements = document.querySelectorAll(".class-name");
```

### Modifiera element

#### Text och HTML-innehåll

```javascript
// Ändra text (hanterar inte HTML-taggar)
element.innerText = "Ny text";

// Ändra HTML-innehåll (kan inkludera HTML-taggar)
element.innerHTML = "<strong>Fet text</strong>";

// Lägg till text i slutet
element.innerText += " mer text";
```

#### CSS-klasser

```javascript
// Lägg till en klass
element.classList.add("new-class");

// Ta bort en klass
element.classList.remove("old-class");

// Växla en klass (lägger till om den inte finns, tar bort om den finns)
element.classList.toggle("some-class");

// Kolla om ett element har en specifik klass
let hasClass = element.classList.contains("some-class");
```

#### Attribut

```javascript
// Sätt attribut
element.setAttribute("data-id", "123");

// Hämta attributvärde
let value = element.getAttribute("data-id");

// Ta bort attribut
element.removeAttribute("data-id");

// Direkta attribut-properties
element.id = "new-id";
element.src = "image.jpg";
element.href = "https://example.com";
```

### Hantera events

Events låter dig köra kod vid olika händelser. En listener är en funktion som anropas vid en händelse, som ett knapptryck exempelvis.

```javascript
// Grundläggande event-listener
element.addEventListener("click", function(event) {
  console.log("Element klickades!");
});

// Med separat funktion
function handleClick(event) {
  console.log("Knapp klickades!");
  console.log("Event-typ:", event.type);
  console.log("Target-element:", event.target);
}
buttonElement.addEventListener("click", handleClick);

// Ta bort event-listener
element.removeEventListener("click", handleClick);
```

Vanliga event-typer:

- `click`: När elementet klickas
- `mouseenter`: När muspekaren går in över elementet
- `mouseleave`: När muspekaren lämnar elementet
- `submit`: När ett formulär skickas
- `input`: När värdet i ett input-fält ändras
- `keydown`: När en tangent trycks ner
- `keyup`: När en tangent släpps upp

### Styling

```javascript
// Ändra en specifik CSS-egenskap
element.style.backgroundColor = "red";
element.style.fontSize = "16px";
element.style.display = "none";

// Hämta styles
let styles = window.getComputedStyle(element);
let fontSize = styles.fontSize;
```

### Dimensioner och position

```javascript
// Hämta element-dimensioner inklusive padding och border
let height = element.offsetHeight;
let width = element.offsetWidth;

// Hämta element-position relativt till närmaste positionerade parent
let top = element.offsetTop;
let left = element.offsetLeft;

// Hämta element-dimensioner inklusive padding men utan border
let clientHeight = element.clientHeight;
let clientWidth = element.clientWidth;

// Hämta element-position och dimensioner relativt till viewport
let rect = element.getBoundingClientRect();
```
