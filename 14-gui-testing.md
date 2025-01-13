# GUI Testing med Jest och jsdom

Jest är ett populärt testramverk för JavaScript som tillsammans med jsdom möjliggör omfattande testning av GUIs. jsdom implementerar DOM-standarden vilket gör det möjligt att simulera en webbläsare utan att behöva en riktig webbläsare.

## NodeJS och Node Package Manager

# GUI Testing med Jest och jsdom

## Node.js och NPM

Node.js är en JavaScript-runtime som gör det möjligt att köra JavaScript utanför webbläsaren. Node.js används främst för att bygga servrar och utvecklingsverktyg, och det kan användas som testmiljö också.

NPM (Node Package Manager) är Node.js pakethanterare och världens största mjukvarubibliotek. Det används för att:

- Installera JavaScript-bibliotek och verktyg
- Hantera projektberoenden
- Köra scripts definierade i package.json
- Publicera och dela kod med andra utvecklare

Grundläggande NPM-kommandon:

```sh
# Initiera ett nytt projekt
npm init

# Installera paket (exempelvis jest och jsdom)
npm install jest jsdom

# Kör script definierat i package.json
npm run test

# Uppdatera alla paket
npm update
```

`package.json` är en fil som håller koll på script, paket och andra saker. En sådan kan se ut såhär:

```json
{
  "name": "project-name",
  "version": "1.0.0",
  "scripts": {
    "test": "jest",
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.17.1"
  },
  "devDependencies": {
    "jest": "^27.0.0",
    "jsdom": "^16.5.0"
  }
}
```

## Grundläggande Setup

För att komma igång med GUI-testning behöver du installera både Jest och jsdom genom NodeJS:

```sh
npm install --save-dev jest jsdom
```

Konfigurera Jest i din `package.json` eller `jest.config.js`:

```javascript
module.exports = {
  testEnvironment: "jsdom",
  setupFilesAfterEnv: ["./jest.setup.js"],
};
```

## Skapa en Testmiljö

I din `jest.setup.js` kan du konfigurera den globala testmiljön:

```javascript
import "@testing-library/jest-dom";

global.document = window.document;
global.window = window;
```

## Grundläggande GUI-testning

### Rendera och Testa Element

```javascript
describe("GUI Tests", () => {
  beforeEach(() => {
    document.body.innerHTML = `
      <div id="app">
        <button id="counter">0</button>
      </div>
    `;
  });

  test("button click increases counter", () => {
    const button = document.getElementById("counter");
    const initialValue = Number(button.textContent);

    button.click();

    expect(Number(button.textContent)).toBe(initialValue + 1);
  });
});
```

### Simulera Användarinteraktioner

Jest och jsdom stödjer simulering av olika användarinteraktioner:

```javascript
// Clicks
element.click();

// Inputs
const input = document.querySelector("input");
input.value = "test text";
input.dispatchEvent(new Event("input"));

// Keys
element.dispatchEvent(
  new KeyboardEvent("keydown", {
    key: "Enter",
    code: "Enter",
    keyCode: 13,
  }),
);
```

## Tips

1. Rensa DOM:en mellan tester:

```javascript
afterEach(() => {
  document.body.innerHTML = "";
});
```

2. Testa hellre användarbeteende än implementation:

```javascript
// Bra
test("user can submit form", () => {
  fillFormFields();
  submitForm();
  expectSuccessMessage();
});

// Mindre bra
test("submitForm sets isSubmitted to true", () => {
  expect(form.isSubmitted).toBe(true);
});
```
