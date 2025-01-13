# Introduktion till JavaScript

JavaScript är ett programmeringsspråk som används på webben för att tillägga funktionalitet till webbsidor. Med HTML och CSS kan du lägga till knappar, tabeller, listor, formulär och mycket mer, men de gör inget förutom att visa information. Om du vill kunna trycka på knappar och se saker hända så måste du använda JavaScript.

Till skillnad från HTML, som är ett markupspråk, och CSS, som är ett designspråk, så är JavaScript ett "riktigt" programmeringsspråk. Genom kod så säger du åt vad datorn skall göra. Allt går ut på att skriva instruktioner till datorn som sedan utför dem i en viss ordning.

JavaScript är konceptuellt likt andra språk, och syntaxen är också rätt så vanlig. Följande är några centrala koncept som finns i JavaScript:

- datatyper
- operatörer
- variabler
- if-satser
- switch-satser
- objekt
- arrayer
- funktioner

## Debug output

Det är vanligt att "skriva ut till konsolen" i JavaScript. Det används för att få information om olika saker. Det finns två sätt att göra detta på:

```javascript
console.log("Exempel 1");
```

... eller:

```javascript
alert("Exempel 2");
```

Innanför `()` kan du skriva nästan vad som helst: strängar, nummer, booleans, objekt, arrayer och mer. Mer information om dessa finns i kommande delar. Testa gärna ovanstående kod själv och se vad som händer. Du behöver öppna konsolen i webbläsaren för att se `console.log` outputs. Du gör detta genom att högerklicka på webbsidan och ta "Inspect" eller liknande, och gå till "Console" fliken.

`console.log` och `alert` används endast i debug syfte.

## Debug input

Det är vanligt att behöva hämta information från användaren. Det kan man göra med exempelvis formulär. Men formulär är ganska avancerade till att börja med så det är mycket enklare att istället använda en annan metod: `prompt()`. Det kan användas såhär:

```javascript
let userInput = prompt("Skriv in något:");
```

Svaret av `prompt()` är en sträng med det användaren skrev in i popup-fönstret. Testa gärna ovanstående kod själv för att se vad som händer.

`prompt` används endast i debug syfte.

## Kommentarer

Det finns två sätt att skriva kommentarer på i JavaScript: en rads kommentarer och flerrads kommentarer.

En rad:

```javascript
// This is a comment
console.log("Some code");
// Everything after double slashes counts as a comment
```

För flera rader:

```javascript
/*
This
is
a
multi
line
comment
*/

console.log("Some code");

/*
Everything between the slash+star signs counts as a comment.
*/
```

## Datatyper

I programmering behöver man ofta spara saker ("komma ihåg" saker, vilket man tilldel gör med variabler). Men JavaScript behöver veta vad du vill spara - det som säger vad som skall sparas är datatyper. En datatyp är en typ av data som gör att datorn förstår vad datan är. Följande datatyper finns i JavaScript:

- `Number` - Kan spara alla sorters nummer
- `String` - Kan spara text
- `Boolean` - Kan spara ett `true` eller `false` värde (av eller på)
- `Array` - Kan spara flera värden av alla datatyper
- `Objekt` - Kan spara flera värden av alla datatyper, och alla värden har namn (som variabler)
- `Undefined` & `null` - Två speciella datatyper, som också räknas som värden. De används för att informera att ett annat värde inte finns

Om du behöver spara någons namn exempelvis så använder du `String` eftersom den sparar text. Om du behöver spara någons ålder så använder du `Number`. Du bestämmer datatyp när du skapar en variabel. Följande sektioner förklarar lite mer om varje datatyp. Kom ihåg att en datatyp av sig själv inte är användbar, det är bara när de kombineras med exempelvis variabler som de fungerar.

Läs mer nedanför och läs sedan om variabler för att förstå bättre hur datatyper används.

### Number

`Number` datatypen identifieras genom nummer direkt. Om du skriver ett nummer så kommer det att betraktas av JavaScript som ett nummer. Exempel:

```javascript
1;
```

```javascript
3.14;
```

```javascript
482803;
```

```javascript
-543;
```

```javascript
0.0082;
```

### String

`String` datatypen identifieras genom dubbelcitat tecken. Om du skriver `""` så kommer det att betraktas av JavaScript som en sträng. Exempel:

```javascript
"Hello World!";
```

```javascript
"Godis och glass är gott";
```

```javascript
"A";
```

```javascript
"1";
```

_Notera: Även om det står ett så blir det en sträng eftersom det ligger innanför `""`_

```javascript
"fh---^ÖÄ*74830yb78c302ydr780432yr78032";
```

### Boolean

`Boolean` datatypen identifieras genom `true` och `false`. Om du skriver `true` eller `false` så kommer det att betraktas av JavaScript som en boolean. Exempel:

```javascript
true;
```

```javascript
false;
```

### Array

`Array` datatypen identifieras genom hakparanteser. Om du skriver `[]` så kommer det att betraktas av JavaScript som en array. Exempel:

```javascript
[];
```

Arrayer kan också innehålla saker, så följande är också arrayer:

```javascript
[1, 2, 3];
```

```javascript
[1, "Godis", true];
```

```javascript
["I", "Like", "Candy"];
```

Arrayer har en egen sektion längre ned som innehåller mer information.

### Object

`Object` datatypen identifieras genom måsvingar. Om du skriver `{}` så kommer det att betraktas av JavaScript som ett objekt. Exempel:

```javascript
{
}
```

_Notera: Om du bara har måsvingar räknas det som ett objekt. Måsvingar på if-satser, funktioner och annat är dock orelaterade och har inget med objekt att göra_

Objekt kan också innehålla saker, så följande är också objekt:

```javascript
{
    name: "Ironman",
    age: 34,
}
```

```javascript
{
    favoriteFood: "Tacos",
    mealsPerDay: 3
}
```

```javascript
{
    a: "a",
    b: 6
}
```

Objekt har en egen sektion längre ned som innehåller mer information.

### Undefined och null

`Undefined` identifieras genom `undefined` och `Null` genom `null`. Exempel:

```javascript
undefined;
```

```javascript
null;
```

Dessa är speciella. De används för att signalera att ett annat värde inte kan hittas eller finns. Om du exempelvis programmerar en sökfunktion för filmer och söker efter en film som inte finns så kan du använda `null` som värde för att signalera att filmen du sökte efter inte finns.

Undefined kan också användas för att signalera att ett värde inte är definierat än. Detta blir default på variabler exempelvis:

```javascript
let myVariable; // Denna får `undefined` som värde eftersom inget annat har bestämts.
```

## Variabler

Variabler är ett sätt att säga åt datorn att komma ihåg saker. Om du exempelvis behöver komma ihåg någons ålder så kan du göra det med en variabel. Varje variabel har en datatyp som säger åt JavaScript hur den kan hantera variabeln. Syntaxen för variabler är som följande:

```javascript
let variableName = "value";
```

Det börjar med `let` vilket är nyckelordet som används för att skapa en ny variabel. Nyckelordet följs upp med namnet på variabeln, vilket används för att kunna referera till variabeln på andra ställen. Det följs upp med `=` som används för att sätta värdet på variabeln, och det som följer efter det är själva värdet som du vill att variabeln ska få. Värdet måste vara av en av datatyperna som JavaScript tillåter. Om du vill skapa en sträng så använder du dubbelcitat tecken (""). Om du vill skapa ett nummer så skriver du nummret rakt ut:

```javascript
let myAge = 34;
```

Syftet med variabler är att kunna komma ihåg saker och att kunna återanvända information. Ta följande exempel som visar varför återanvändbarhet är viktigt. Låtsas att du vill skriva ut ditt namn 10 gånger:

```javascript
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
console.log("Ironman");
```

... men att du i efterhand byter namn:

```javascript
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
console.log("Batman");
```

Det blir väldigt jobbigt att göra detta för hand varje gång. Om du istället använder en variabel så kan du enkelt byta namn:

```javascript
let name = "Ironman";
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
```

... vilket enkelt byts, genom en enda rad, såhär:

```javascript
let name = "Batman";
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
console.log(name);
```

Alltså, du behöver endast ändra på en rad genom variabler, till skillnad från alla tio rader med den första metoden. Självklart så visar sig liknande situationer väldigt sällan, men det är fortfarande väldigt vanligt att man behöver referera till samma värde (variabel) på flera ställen i kod.

Det som gör att variabler kan återanvändas är ju möjligheten att referera till dem. Om du skriver följande:

```javascript
let superhero = "Ironman";
console.log(superhero); // Printar "Ironman", vilket är som om man skrivit `console.log("Ironman");`
```

... så kommer "Ironman" att printas ut eftersom `console.log` får en referens till `superhero`, som innehåller "Ironman" som värde.

Detta fungerar oavsett datatyp, exempel:

```javascript
let aNumber = 8;
console.log(aNumber); // Printar 8.
```

```javascript
let anArray = [];
console.log(anArray); // Printar [].
```

### Konstanter

`let` nyckelordet används för att skapa en variabel. Men det finns också ett annat sätt: `const`. Det skrivs på samma sätt:

```javascript
const variableName = "value";
```

Skillnaden mellan `let` och `const` är att du kan ändra på värdet på `let` variabler, vilket du inte kan göra med `const`. Ta följande exempel:

```javascript
const myVar = 5;
myVar = 7; // Detta går inte på grund av `const`.
```

... du kan alltså inte byta värde på en `const` efter att du har skapat den. Använd `const` när du behöver konstanter. Exempel på konstanter som finns i den matematiska världen är `PI` och `e`. Du kan också skapa dina egna konstanter, och de behöver inte vara nummer.

### Namngivningsregler

Man kan inte välja vilka namn som helst på variabler. Du kan exempelvis inte skapa en variabel med ett namn som börjar på ett nummer och du kan heller inte skriva namn som innehåller mellanslag.

Det finns också oskrivna regler på hur man ska skriva variabler. JavaScript brukar följa camelCase regler. Camel case betyder att du skriver ord som namn, och det första ordet innehåller små bokstäver. Varje ord som följer skall börja med en stor bokstav. Om du exempelvis vill ge namnet `I like dogs` till en variabel så skulle du med camelCase skriva: `iLikeDogs`.

## Operatörer

Operatörer används för att göra uträkningar mellan två värden, och de kan kombineras flera gånger för att göra uträkningar mellan fler värden (än bara två). Den enklaste operatören är `+`, vilket adderar två tal och returnerar summan:

```javascript
1 + 1; // Blir 2
```

... eller om man vill räkna ut summan för flera tal:

```javascript
1 + 1 + 2 + 5 + 8;
```

Operatörer är inte användbara av sig själva så de brukar användas med variabler för att spara resultat. Om du exempelvis vill addera två tal så vill du ju också veta vad svaret blir, och därför så sparar du det i en variabel.

Följande operatörer finns i JavaScript:

- `+` Addition
- `-` Subtraktion
- `*` Multiplikation
- `/` Division
- `=` Tilldelning (används för variabler)
- `<` Mindre än (jämför två tal A och B och returnerar true om A är mindre än B)
- `>` Mindre än (jämför två tal A och B och returnerar true om A är större än B)
- `<=` Mindre än eller lika med (jämför två tal A och B och returnerar true om A är mindre än B ELLER om A är samma som B)
- `>=` Mindre än eller lika med (jämför två tal A och B och returnerar true om A är större än B ELLER om A är samma som B)

Så länge en operatör returnerar samma datayp som en annan så kan de kombineras:

```javascript
1 + 3 - (3 * 7) / 2;
```

Du kan däremot inte kombinera operatörer relaterade till exempelvis `Boolean` datatypen och `Number` datatypen eftersom de är olika. Följande blir alltså konstigt:

```javascript
!true + 5 / false;
```

## Arrayer

En array är en datatyp som kan hålla flera värden. De definieras med `[]` och kan se ut såhär:

```javascript
let emptyArray = [];
let arrayOfNumbers = [4, 2, 9, 6];
let arrayOfStrings = ["A", "Hej", "Hello World", "Ironman"];
let arrayOfMixedTypes = [1, "Hej", 8, true, {}];
let arrayOfArrays = [[true, 2, "Hello"], [1, 5, 9], ["Hej"]];
```

Varje värde i en array kallas `element`. Varje `element` har en position som kallas `index`. Index börjar alltid på `0`. Se följande exempel:

```javascript
// Index:
//            0    1    2    3
let array = ["A", "B", "C", "D"];
```

För att komma åt ett `element` i en array används `index`:

```javascript
let array = ["A", "B", "C", "D"];

let elementA = array[0]; // Blir "A"
let elementB = array[1]; // Blir "B"
let elementD = array[3]; // Blir "D"
```

Detta kan även användas för att ändra värde på en viss position:

```javascript
let array = ["A", "B", "C", "D"];

array[0] = "Q";
array[2] = "G";

// Arrayen ser nu ut såhär: ["Q", "B", "G", "D"]
```

### Array funktioner

Hela poängen med arrayer är att kunna spara flera värden, men det är inte så användbart om man måste hårdkoda antalet. Därför finns det funktioner som lägger till mer funktionalitet.

Lägg till ett nytt element i en array med `.push()`:

```javascript
let someArray = [];
someArray.push("My new value");
someArray.push("Another value");
```

Ta bort element från en array med `.splice()` vilket tar in två argument. Argument ett bestämmer vilket index som ska tas bort och argument två bestämmer hur många element som ska bort. Se följande exempel:

```javascript
let someArray = [1, 2, 3];
someArray.splice(0, 1); // Raderar `1`.
someArray.splice(0, 1); // Raderar `2` eftersom tvåan har flyttats till första platsen.
someArray.splice(0, 1); // Raderar `3` eftersom trean nu har flyttats till första platsen, då både ett och två är raderade.

// Ny array
someArray = [1, 2, 3];
someArray.splice(1, 2); // Börjar på index 1 och raderar två element. Raderar därför `2` och `3`.
```

Det finns även många fler funktioner. Referera till [dokumentationen](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) för mer information.

## Villkorssatser (if-satser)

Villkorssatser är sätt att köra kod baserat på villkor. Om du som ett simpelt exempel vill skriva ut rekommendationer baserat på en temperatur med kod, så skulle det kunna se ut såhär:

```javascript
let temperature = ?; // Låtsas att värdet här är slumpat.

if (temperature >= 30) {
    console.log("Go swimming. It is very hot outside!");
} else if (temperature >= 20) {
    console.log("Wear something light.");
} else if (temperature >= 10) {
    console.log("Wear a light jacket.");
} else if (temperature >= 0) {
    console.log("Wear pants and a light jacket.");
} else {
    console.log("Wear a thick jacket, it is cold outside");
}
```

Det finns tre typer av villkorssatser (egentligen finns det mer, men endast if-satser visas i detta dokument): `if`, `else if` och `else`.

---

`if` är alltid det första man skriver, och `else if` samt `else` är valfria. Både `if` och `else if` tar in en boolean. Om värdet är `true` så exekveras if-satsen. Ta följande exempel:

```javascript
let age = 5;
if (age === 4) {
  console.log("Detta kommer INTE skrivas ut, eftersom age inte är fyra.");
}

if (age > 3) {
  console.log("Denna kommer att exekveras eftersom age är större än tre.");
}
```

`else if` kan läggas på en `if` valfritt antal gånger. En `else if` exekveras bara om:

1. Alla `if` och `else if` satser innan den **inte** har exekverats
2. Villkoret för `else if`-satsen är `true`

Exempel 1:

```javascript
let age = 5;
if (age === 4) {
  console.log("Detta kommer INTE skrivas ut, eftersom age inte är fyra.");
} else if (age === 3) {
  console.log("Detta kommer INTE skrivas ut, eftersom age inte är tre.");
} else if (age === 5) {
  console.log("Denna kommer att exekveras eftersom age är fem.");
}
```

Exempel 2:

```javascript
let age = 20;
if (age === 19) {
  console.log("Detta kommer INTE skrivas ut.");
} else if (age === 20) {
  console.log("Detta kommer att skrivas ut, eftersom age är 20.");
} else if (age > 10) {
  console.log(
    "Denna kommer INTE att exekveras, även om den är sann, eftersom else if-satsen innan redan har exekverats.",
  );
}
```

`else` kan läggas på max en gång på `if` eller `else if`. En `else` sats exekveras bara om **ingen** tidigare `if` eller `else if` har exekverats.

Exempel 1:

```javascript
let age = 5;
if (age === 4) {
  console.log("Detta kommer INTE skrivas ut, eftersom age inte är fyra.");
} else {
  console.log(
    "Denna kommer att exekveras automatiskt eftersom if-satsen inte exekverades.",
  );
}
```

Exempel 2:

```javascript
let age = 20;
if (age === 20) {
  console.log("Detta kommer att skrivas ut.");
} else {
  console.log("Denna exekveras INTE eftersom if-satser gick igenom.");
}
```

## Loopar

Loopar är till för att upprepa en kod ett antal gånger. Om du exempelvis vill räkna från 0 till 100 och skriva ut alla tal emellan med `console.log` så kan du lösa det enkelt med en loop, istället för att behöva skriva in allt manuellt som följande:

```javascript
console.log(1);
console.log(2);
console.log(3);
console.log(4);
console.log(5);
console.log(6);
// ... och så vidare
```

Med en loop kan du skriva:

```javascript
for (let i = 1; i <= 100; i++) {
  console.log(i);
}
```

... vilket endast är tre rader kod (för att skriva ut alla 100 tal).

### Typer

Det finns två typer av loopar i JavaScript: for och while. De båda gör samma sak men på lite olika sätt, och därför passar de olika bra i olika situationer. Men, vad du kan göra med en `for` loop kan du också göra med en `while` loop, och vice-versa.

#### For loop

En for loop består av tre komponenter:

1. Variabel (kallas `initialization`)
2. Villkor (kallas `condition`)
3. Allmänt uttryck (kallas `afterthought`)

Om man vill kan man inkludera innehållet som en komponent. Innehållet är all kod som går innanför måsvingarna på loopen.

Det ser ut som följande (syntax):

```javascript
for (initialization; condition; afterthought) {
  // code...
}
```

... och ett riktigt kod exempel kan se ut såhär:

```javascript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

... vilket räknar från 1 till 10.

Mittersta delen av en for loop (villkoret) bestämmer hur många gånger loopen ska repeteras. Koden där måste vara ett villkor (alltså så måste den returnera `true` eller `false`). En for loop kommer att upprepas så länge villkoret returnerar `true`. Följande loop kommer att upprepas för all tid:

```javascript
for (let i = 0; true; i++) {
  // code...
}
```

Följande loop kommer aldrig att köras (inte ens en gång):

```javascript
for (let i = 0; false; i++) {
  // code...
}
```

Innan varje iteration (upprepning) så checkas villkoret. Om villkoret returnerar `true` så görs en upprepning, och om det returnerar `false` så avbryts loopen.

Den första delen (variabeln) körs innan allt annat, precis innan loopen börjar, och den körs bara en gång. Den sista delen (allmänt uttryck) körs efter varje iteration (efter varje upprepning). Flödet för en for loop är som följande:

```
1. Kör initialization
2. Testa villkor
3.1 Om villkor = true, kör innehållet (koden innanför måsvingar)
3.2 Om villkor = false, avbryt
4. Kör afterthought koden
5. Repetera från steg 2 (eftersom steg 1 endast ska köras en gång)
```

#### While loop

En while loop består av en komponent:

1. Villkor (kallas `condition`)

Om man vill kan man inkludera innehållet som en komponent. Innehållet är all kod som går innanför måsvingarna på loopen.

Det ser ut som följande (syntax):

```javascript
while (condition) {
  // code...
}
```

... och ett riktigt kod exempel kan se ut såhär:

```javascript
let i = 1;
while (i <= 10) {
  console.log(i);
  i++;
}
```

... vilket räknar från 1 till 10.

_Notera: Variabeln och `i++` är egentligen inte en del av loopen i sig_

Villkoret bestämmer hur många gånger loopen ska repeteras. Koden där måste vara ett villkor (alltså så måste den returnera `true` eller `false`). En while loop kommer att upprepas så länge villkoret returnerar `true`. Följande loop kommer att upprepas för all tid:

```javascript
while (true) {
  // code...
}
```

Följande loop kommer aldrig att köras (inte ens en gång):

```javascript
while (false) {
  // code...
}
```

Innan varje iteration (upprepning) så checkas villkoret. Om villkoret returnerar `true` så görs en upprepning, och om det returnerar `false` så avbryts loopen.

Flödet för en while loop är som följande:

```
1. Testa villkor
2.1 Om villkor = true, kör innehållet (koden innanför måsvingar)
2.2 Om villkor = false, avbryt
3. Repetera från steg 2 (eftersom steg 1 endast ska köras en gång)
```

### Arrayer och loopar

Loopar brukar användas tillsammans med arrayer. Det är vanligt att leta efter element i en array med loopar exempelvis, då loopar passar bra med index.

## Funktioner

Funktioner är till för att organisera kod bättre. De är också bra för att kunna återanvända kod. En funktion är egentligen bara som en behållare av kod, och de gör inget av sig själva. De kan se ut såhär:

```javascript
function printHello() {
  console.log("Hello World!");
}
```

Syntax för funktioner består av fyra delar:

1. `function` nyckelordet som definierar funktionen.
2. Namnet på funktionen (ovanför är `printHello` namnet på funktionen). Namn på funktioner är samma som namn för variabler, de är valfria och används för att kunna referera till dem.
3. Paranteser `()`. Innanför dessa lägger man parametrar om man har några. Mer information om parametrar finns längre ned.
4. Kroppen `{}`. Efter paranteser så ska måsvingar finnas och innanför måsvingarna lägger man koden för funktionen.

Om du skapar en funktion, som funktionen i det första exemplet ovanför, så händer inget eftersom funktionen av sig självt inte gör något. Det man gör är att anroppa dem för att "aktivera" koden. För att anroppa funktionen så skriver man `<funktion namn>()`. Ett exempel:

```javascript
// Definiera funktion
function favoriteHero() {
  console.log("My favorite hero is Ironman!");
}

// Anroppa funktion
favoriteHero();
```

Ibland använder man "kalla", "exekvera", "köra" och "aktivera" som synonymer till att "anroppa" funktioner. På engelska kan man säga: "call function", "execute function", "activate function", "run function" och "invoke function". Alla betyder samma sak: att anroppa en funktion, vilket betyder att man kör koden innanför funktionen.

### Parametrar

En parameter är en bit information som kan skickas in i en funktion. Låtsas att du vill skapa en funktion som summerar två tal. Du kan skriva:

```javascript
function sum() {
  let sum = 4 + 3;
  console.log(sum);
}
```

Problemet är att du nu bara kan summera `4` och `3`. Om du vill summera andra tal så kan du skapa fler funktioner. Eller, så använder du parametrar:

```javascript
// firstNumber och secondNumber kallas parametrar.
function sum(firstNumber, secondNumber) {
  let sum = firstNumber + secondNumber;
  console.log(sum);
}

// De värden som skickas in (se nedanför) kallas argument.
sum(2, 3);
sum(-4, 7);
sum(0.5, 0.5);
sum(2, 2);
```

... vilket gör så att du kan återanvända samma funktion flera gånger.

### Return

Return är ett sätt att sluta exekvera kod i en funktion och det kan också användas för att skicka tillbaka värden. Skriv `return;` för att sluta exekvera en funktion:

```javascript
function printIfFiveStopIfThree(num) {
  if (num === 3) {
    return;
  }

  if (num === 5) {
    console.log("Five");
    return;
  }

  console.log("Other number");
}

printIfFiveStopIfThree(3); // Gör inget på grund av if + return.
printIfFiveStopIfThree(5); // Printar "Five" och avslutar sedan koden på grund av return.
printIfFiveStopIfThree(8); // Printar "Other number".
```

Det går även att "returnera" värden med `return`:

Exempel 1:

```javascript
function sum(a, b) {
  return a + b;
}

let result1 = sum(1, 1); // Blir 2
let result2 = sum(3, 5); // Blir 8
```

Exempel 2:

```javascript
function greet(name) {
  return "Hello, " + name;
}

let result1 = greet("Ironman"); // Blir "Hello, Ironman"
let result2 = greet("Flash"); // Blir "Hello, Flash"
```

Exempel 3:

```javascript
function myFunction(number) {
  if (number === 1) {
    return "A";
  } else if (number === 2) {
    return "B";
  } else {
    return "C";
  }
}

let result1 = myFunction(1); // Blir "A"
let result2 = myFunction(2); // Blir "B"
let result3 = myFunction(3); // Blir "C"
let result4 = myFunction(4); // Blir "C"
```

## Objekt

Ett objekt är en datatyp som innehåller en samling med variabler (de kan också ha funktioner men det tas inte upp här). De är bra till att gruppera information.

Om du exempelvis vill hantera information om en person så kan du skapa variabler:

```javascript
let age = 35;
let name = "Ironman";
let gender = "Male";
let height = 183;
```

... men detta blir väldigt svårt att hantera, speciellt om man har ännu fler saker att hålla koll på. Det hade varit bättre att kunna paketera all information till "en sak", så att man kan hantera den istället. Det är det objekt är till för, och med objekt kan du skriva:

```javascript
let personInfo = {
  age: 35,
  name: "Ironman",
  gender: "Male",
  height: 183,
};
```

... vilket paketerar all information till objektet, och objektet kan du hantera som "en sak". Det är som att lägga saker i en låda. Istället för att behöva bära på en massa småsaker utan hjälpmedel så lägger du dem i en låda och bär lådan, vilket blir enklare.

Variabler i objekt kallas egenskaper eller medlemmar.

### Dot selector

När du lägger variabler i objekt så kommer du åt dem genom en dot selector. En dot selector är en punkt efter namnet på variabeln som håller objektet. Om du exempelvis har följande objekt:

```javascript
let person = {
  name: "Ironman",
  age: 34,
};
```

... så kan du komma åt `name` variabeln genom:

```javascript
console.log(person.name);
```

Detta gäller för alla objekt variabler.
