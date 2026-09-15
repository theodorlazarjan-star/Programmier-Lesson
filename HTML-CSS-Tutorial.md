# HTML & CSS – Kurzreferenz

Eine kompakte Übersicht zum Wiederholen der wichtigsten HTML- und CSS-Grundlagen.

---

## 1. HTML-Grundstruktur

```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meine Website</title>
    <link rel="icon" type="image/png" href="favicon.png">
    <link rel="stylesheet" href="style.css">
</head>
<body>

</body>
</html>
```

- `<!DOCTYPE html>` → HTML5
- `<html>` → gesamte Seite
- `<head>` → Informationen für den Browser
- `<title>` → Browser-Tab
- `<body>` → sichtbarer Inhalt
- `<link>` → externe Dateien verbinden

Kommentar:

```html
<!-- Das ist ein Kommentar -->
```

---

## 2. Überschriften & Text

```html
<h1>Hauptüberschrift</h1>
<h2>Unterüberschrift</h2>
<h3>...</h3>
<h4>...</h4>
<h5>...</h5>
<h6>...</h6>

<p>Ein Absatz.</p>
<br>
<hr>
```

- `<br>` → Zeilenumbruch
- `<hr>` → Trennlinie
- `<pre>` → behält Leerzeichen und Zeilenumbrüche

```html
<pre>
Zeile 1
    Zeile 2
</pre>
```

---

## 3. Text formatieren

```html
<strong>Wichtig</strong>
<em>Betont</em>
<b>Fett</b>
<i>Kursiv</i>
<u>Unterstrichen</u>
<del>Gelöscht</del>
<small>Kleiner Text</small>
<mark>Markiert</mark>

H<sub>2</sub>O
x<sup>2</sup>

<code>console.log("Hello");</code>
```

`<strong>` und `<em>` sind meist besser als `<b>` und `<i>`, weil sie zusätzlich Bedeutung vermitteln.

---

## 4. Links

```html
<a href="https://example.com">Website</a>

<a href="https://example.com" target="_blank">
    Neue Seite
</a>

<a href="mailto:test@example.com">
    E-Mail
</a>
```

- `href` → Ziel
- `target="_blank"` → neuer Tab
- `title` → Tooltip

Relative Links:

```html
<a href="about.html">Über mich</a>
```

---

## 5. Bilder

```html
<img src="bild.jpg"
     alt="Beschreibung des Bildes"
     width="300"
     height="200">
```

`alt` ist wichtig für Barrierefreiheit und falls das Bild nicht geladen wird.

Bild als Link:

```html
<a href="bild.jpg">
    <img src="bild.jpg" alt="Bild">
</a>
```

---

## 6. Audio & Video

### Audio

```html
<audio controls loop>
    <source src="musik.mp3" type="audio/mpeg">
</audio>
```

### Video

```html
<video controls width="500">
    <source src="video.mp4" type="video/mp4">
</video>
```

---

## 7. Listen

### Ungeordnete Liste

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

### Geordnete Liste

```html
<ol>
    <li>HTML lernen</li>
    <li>CSS lernen</li>
</ol>
```

### Verschachtelte Liste

```html
<ul>
    <li>Frontend
        <ul>
            <li>HTML</li>
            <li>CSS</li>
        </ul>
    </li>
</ul>
```

### Beschreibungsliste

```html
<dl>
    <dt>HTML</dt>
    <dd>Struktur einer Website</dd>

    <dt>CSS</dt>
    <dd>Aussehen einer Website</dd>
</dl>
```

---

## 8. Tabellen

```html
<table>
    <caption>Meine Tabelle</caption>

    <thead>
        <tr>
            <th>Name</th>
            <th>Alter</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Max</td>
            <td>20</td>
        </tr>
    </tbody>
</table>
```

- `<table>` → Tabelle
- `<tr>` → Zeile
- `<th>` → Überschrift
- `<td>` → normale Zelle
- `<thead>` → Kopfbereich
- `<tbody>` → Inhalt
- `<caption>` → Tabellenüberschrift

Aussehen mit CSS gestalten, nicht mit alten HTML-Attributen wie `border` oder `align`.

---

## 9. Formulare

```html
<form action="/submit" method="post">

    <label for="name">Name:</label>
    <input id="name" name="name" type="text" required>

    <input type="email" name="email">
    <input type="password" name="password">
    <input type="tel" name="phone">
    <input type="date" name="date">
    <input type="number" name="age" min="1" max="100">

    <textarea name="message"></textarea>

    <select name="country">
        <option value="de">Deutschland</option>
        <option value="at">Österreich</option>
    </select>

    <input type="checkbox" name="terms">

    <input type="radio" name="gender" value="m">
    <input type="radio" name="gender" value="f">

    <input type="file" name="file">

    <button type="submit">Absenden</button>
    <button type="reset">Zurücksetzen</button>

</form>
```

Wichtige Attribute:

- `id` → eindeutige Identifikation
- `name` → Name der gesendeten Daten
- `value` → Wert
- `placeholder` → Hinweistext
- `required` → Pflichtfeld
- `minlength` / `maxlength` → Textlänge
- `min` / `max` → Zahlenbereich
- `pattern` → bestimmtes Format
- `accept` → erlaubte Dateitypen

Bei Datei-Uploads:

```html
<form method="post" enctype="multipart/form-data">
```

---

## 10. Semantisches HTML

```html
<header>
    Kopfbereich
</header>

<nav>
    Navigation
</nav>

<main>
    Hauptinhalt

    <section>
        Bereich
    </section>

    <article>
        Eigenständiger Inhalt
    </article>

    <aside>
        Zusatzinformationen
    </aside>
</main>

<footer>
    Fußbereich
</footer>
```

Weitere Container:

```html
<div>Block-Container</div>
<span>Inline-Container</span>
```

Semantisches HTML macht die Struktur verständlicher und verbessert Accessibility und SEO.

---

## 11. CSS einbinden

### Extern – empfohlen

HTML:

```html
<link rel="stylesheet" href="style.css">
```

CSS:

```css
body {
    background: lightgray;
}
```

Projekt:

```text
projekt/
├── index.html
└── style.css
```

### Intern

```html
<style>
    body {
        background: lightgray;
    }
</style>
```

### Inline

```html
<p style="color: red;">Text</p>
```

Für normale Projekte: **externes CSS verwenden.**

---

## 12. CSS-Syntax

```css
selector {
    eigenschaft: wert;
}
```

Beispiel:

```css
p {
    color: blue;
    font-size: 20px;
}
```

---

## 13. CSS-Selektoren

### Element

```css
p {
    color: red;
}
```

### Klasse

```css
.text {
    color: red;
}
```

```html
<p class="text">Hallo</p>
```

### ID

```css
#title {
    color: blue;
}
```

```html
<h1 id="title">Hallo</h1>
```

### Element + Klasse

```css
p.text {
    color: green;
}
```

### Nachfahren

```css
div p {
    color: red;
}
```

→ jedes `<p>` innerhalb eines `<div>`

### Direktes Kind

```css
div > p {
    color: blue;
}
```

### Direkt folgendes Geschwister

```css
h1 + p {
    color: green;
}
```

### Allgemeine Geschwister

```css
h1 ~ p {
    color: orange;
}
```

---

## 14. Farben

```css
color: red;
color: #ff0000;
color: rgb(255, 0, 0);
```

```css
color: white;
background-color: black;
```

---

## 15. Schrift

```css
p {
    font-family: Arial, sans-serif;
    font-size: 20px;
    font-weight: bold;
    font-style: italic;
}
```

Fallback:

```css
font-family: Arial, Helvetica, sans-serif;
```

Einheiten:

- `px` → Pixel
- `%` → Prozent
- `em` → relativ zur Schriftgröße des Elements
- `rem` → relativ zur Root-Schriftgröße

---

## 16. Border

```css
.box {
    border: 2px solid black;
    border-radius: 10px;
}
```

Einzelne Seiten:

```css
border-top: 2px solid black;
border-right: 2px solid black;
border-bottom: 2px solid black;
border-left: 2px solid black;
```

---

## 17. Schatten

```css
box-shadow: 5px 5px 10px gray;
```

```css
text-shadow: 2px 2px 5px gray;
```

---

## 18. Box Model

```text
┌──────────────────────────┐
│          margin          │
│  ┌────────────────────┐  │
│  │       border       │  │
│  │  ┌──────────────┐  │  │
│  │  │   padding    │  │  │
│  │  │  ┌────────┐  │  │  │
│  │  │  │content │  │  │  │
│  │  │  └────────┘  │  │  │
│  │  └──────────────┘  │  │
│  └────────────────────┘  │
└──────────────────────────┘
```

- `content` → Inhalt
- `padding` → Abstand innen
- `border` → Rahmen
- `margin` → Abstand außen

```css
.box {
    margin: 20px;
    padding: 20px;
    border: 2px solid black;
}
```

Sehr nützlich:

```css
* {
    box-sizing: border-box;
}
```

---

## 19. Margin & Padding

Ein Wert:

```css
margin: 10px;
```

Vier Werte:

```css
margin: 10px 20px 30px 40px;
```

Reihenfolge:

```text
top right bottom left
```

Auch:

```css
padding-top: 10px;
padding-right: 20px;
```

Zentrieren:

```css
.box {
    width: 500px;
    margin: 0 auto;
}
```

---

## 20. Width, Height & Overflow

```css
.box {
    width: 300px;
    height: 200px;

    min-width: 200px;
    max-width: 600px;

    min-height: 100px;
    max-height: 400px;
}
```

Overflow:

```css
overflow: visible;
overflow: hidden;
overflow: scroll;
overflow: auto;
```

`auto` → Scrollbar nur wenn nötig.

---

## 21. Display

### Block

```css
display: block;
```

Nimmt normalerweise die verfügbare Breite ein.

### Inline

```css
display: inline;
```

Bleibt im Textfluss.

### Inline-Block

```css
display: inline-block;
```

Inline, aber mit Width/Height.

### Entfernen

```css
display: none;
```

Element verschwindet inklusive Platz.

### Unsichtbar

```css
visibility: hidden;
```

Element ist unsichtbar, Platz bleibt erhalten.

---

## 22. Float & Clear

```css
img {
    float: left;
    margin-right: 20px;
}
```

Float beenden:

```css
clear: both;
```

Moderne Layouts verwenden meistens **Flexbox oder Grid** statt Float.

---

## 23. Position

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

### Relative

```css
.box {
    position: relative;
    top: 10px;
}
```

### Absolute

```css
.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

Absolute Elemente orientieren sich meist am nächsten positionierten Vorfahren.

### Fixed

```css
header {
    position: fixed;
    top: 0;
}
```

Bleibt beim Scrollen an einer festen Position.

### Sticky

```css
header {
    position: sticky;
    top: 0;
}
```

Verhält sich zunächst normal und bleibt beim Scrollen an der angegebenen Position.

---

## 24. Hintergrund

```css
body {
    background-image: url("background.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    background-attachment: fixed;
}
```

---

## 25. Pseudo-Klassen

Pseudo-Klassen beschreiben einen Zustand.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}

a:hover {
    color: red;
}

a:active {
    color: orange;
}
```

Weitere:

```css
button:not(.disabled) {
    cursor: pointer;
}

li:nth-child(2) {
    color: red;
}
```

---

## 26. Pseudo-Elemente

```css
p::first-letter {
    font-size: 30px;
}

p::first-line {
    font-weight: bold;
}

::selection {
    background: black;
    color: white;
}
```

Vor/nach Inhalt:

```css
.title::before {
    content: "★ ";
}

.title::after {
    content: " ✓";
}
```

Listenmarker:

```css
li::marker {
    font-size: 20px;
}
```

---

## 27. Dropdown-Menü

HTML:

```html
<div class="dropdown">
    <button>Menü</button>

    <div class="content">
        <a href="#">Home</a>
        <a href="#">About</a>
    </div>
</div>
```

CSS:

```css
.dropdown {
    position: relative;
}

.content {
    display: none;
    position: absolute;
}

.dropdown:hover .content {
    display: block;
}
```

Prinzip:

```text
normal → display: none
hover  → display: block
```

---

## 28. Pagination

HTML:

```html
<div class="pagination">
    <a href="#">«</a>
    <a class="active" href="#">1</a>
    <a href="#">2</a>
    <a href="#">3</a>
    <a href="#">»</a>
</div>
```

CSS:

```css
.pagination a {
    padding: 8px 12px;
    text-decoration: none;
}

.pagination a:hover {
    background: lightgray;
}

.pagination .active {
    background: black;
    color: white;
}
```

---

## 29. HTML + JavaScript

HTML:

```html
<button id="button">Klick mich</button>
<p id="text"></p>
```

JavaScript:

```html
<script>
const button = document.getElementById("button");
const text = document.getElementById("text");

button.addEventListener("click", () => {
    text.textContent = "Hallo!";
});
</script>
```

- HTML → Struktur
- CSS → Aussehen
- JavaScript → Verhalten/Interaktion

---

## 30. Gute Projektstruktur

```text
website/
├── index.html
├── style.css
├── script.js
├── images/
│   ├── logo.png
│   └── photo.jpg
└── README.md
```

HTML:

```html
<link rel="stylesheet" href="style.css">
<script src="script.js" defer></script>
```

---

## 31. CSS-Spezifität

Grundsätzlich:

```text
Inline
  ↓
ID
  ↓
Klasse / Attribut / Pseudo-Klasse
  ↓
Element
```

Beispiel:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#special {
    color: red;
}
```

```html
<p id="special" class="text">Hallo</p>
```

→ `red`, weil die ID spezifischer ist.

Bei gleicher Spezifität gewinnt normalerweise die Regel, die **später** kommt.

---

## 32. Merksatz

```text
HTML       = Struktur
CSS        = Design
JavaScript = Verhalten
```

```text
HTML
 ├── Elemente
 ├── Attribute
 ├── Links
 ├── Bilder
 ├── Formulare
 ├── Tabellen
 └── semantische Struktur

CSS
 ├── Selektoren
 ├── Farben & Schrift
 ├── Box Model
 ├── Display
 ├── Position
 ├── Background
 ├── Pseudo-Klassen
 └── Pseudo-Elemente
```

**Das Wichtigste:** Du musst nicht jeden Code auswendig lernen. Du solltest wissen, was möglich ist und wonach du bei Bedarf suchen musst.
