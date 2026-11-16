Task 3:
my element: form

1. Frage: Which parameters of this DOM element can be accessed from javascript?

Bei einem Formular spricht man hier meistens von Eigenschaften statt von Parametern. Dein Formular hat in der HTML-Datei die `id="myForm"`. In JavaScript kannst du es so auswählen:

```js
const form = document.getElementById("myForm");
```

Danach kann man Eigenschaften des Formulars abrufen, zum Beispiel:

```js
form.id        // "myForm"
form.elements  // alle Eingabefelder und Schaltflächen im Formular
form.action    // Zieladresse, an die das Formular gesendet wird
form.method    // Übertragungsmethode, zum Beispiel "get" oder "post"
```

Man kann auch die Werte der Felder im Formular auslesen:

```js
form.querySelector("#color").value      // ausgewählte Farbe
form.querySelector("#name").value       // eingegebener Name
form.querySelector("#agree").checked    // true, wenn das Kästchen angekreuzt ist
```

Für die Auswahl „Small“ oder „Large“ kann man prüfen, welcher Radiobutton ausgewählt ist:

```js
form.querySelector('input[name="size"]:checked')?.value
```

Das ergibt `"small"` oder `"large"`. Wenn keiner ausgewählt ist, ergibt es `undefined`. Bei einem HTML Formular.

2. Frage: What do these parameters do?

Mit JavaScript kann man ein Formular finden und die Eingaben darin auslesen.

- `form.id` – Wie heißt das Formular?
- `form.elements` – Welche Felder hat es?
- `.value` – Was wurde eingegeben oder ausgewählt?
- `.checked` – Ist ein Kästchen angekreuzt?

Zum Beispiel:

```js
const form = document.getElementById("myForm");
const name = form.querySelector("#name").value;
```

Damit greift man auf das Formular zu und liest den eingegebenen Namen aus.

Was ich noch gelernt habe:

Interaktivität (event.preventDefault()): Mit JavaScript lässt sich das automatische Neuladen der Seite beim Absenden verhindern. So können Eingaben vorab validiert oder per Skript verarbeitet werden (z. B. Auslesen von .value und .checked).

Wie schickt man das Formular dann ab?:
via JS: fetch
HTML:
<form action="zielseite.php" method="POST">
  <input type="text" name="name" value="Michael">
  <button type="submit">Abschicken</button>
</form>

->>
action: Die Adresse, zu der die Daten geschickt werden sollen (z. B. ein Skript auf dem Server).

method: Wie sie geschickt werden (GET oder POST).

Task 5:

button:
Beim Button-Element kann man über JavaScript auf type, disabled, name, value, form und autofocus zugreifen. Mit type legt man fest, ob der Button ein Formular absendet (submit), es zurücksetzt (reset) oder ein normaler Button ist (button). Mit disabled kann man den Button deaktivieren, sodass er nicht mehr klickbar ist. name und value werden beim Absenden des Formulars mitgeschickt. Über form erhält man das Formular, zu dem der Button gehört, und autofocus sorgt dafür, dass der Button beim Laden der Seite automatisch den Fokus bekommt.
Beispiel: document.querySelector("button").disabled = true; deaktiviert den Button.

input:
Das Input-Element hat sehr viele Eigenschaften. Mit type bestimmt man die Art des Eingabefeldes, zum Beispiel text, password, number, email, checkbox, radio, file oder date. value enthält den aktuellen Inhalt des Feldes, defaultValue den ursprünglichen Wert aus dem HTML. name ist der Name, unter dem der Wert gesendet wird, und placeholder ist der graue Hinweistext in einem leeren Feld. Bei Checkboxen und Radio-Buttons gibt checked an, ob das Feld angehakt ist. Mit disabled wird das Feld gesperrt, mit readOnly kann man es nur noch lesen, und required macht es zum Pflichtfeld. Mit min, max und step legt man bei Zahlen und Daten Grenzen und Schrittweite fest, mit minLength und maxLength die erlaubte Textlänge. Über pattern kann man einen regulären Ausdruck zur Überprüfung angeben. Bei Datei-Feldern enthält files die ausgewählten Dateien. Mit den Methoden focus(), blur() und select() setzt oder entfernt man den Fokus bzw. markiert den Text.
Beispiel: let name = document.querySelector("input").value; liest den eingegebenen Text aus.

div:
Das Div-Element ist ein reiner Container und hat praktisch keine eigenen Eigenschaften. Man verwendet die allgemeinen Eigenschaften, die alle HTML-Elemente besitzen: id, className und classList für CSS-Klassen, style für Inline-CSS, innerHTML für den HTML-Inhalt, textContent für den reinen Text, hidden zum Ausblenden und children für die enthaltenen Elemente. Mit Methoden wie appendChild() oder remove() kann man Inhalte hinzufügen oder entfernen.
Beispiel: document.querySelector("div").textContent = "Hallo Welt"; schreibt einen neuen Text in das Div.

table:
Beim Table-Element kann man über rows auf alle Zeilen der Tabelle zugreifen, über tBodies auf die Tabellenkörper und über tHead und tFoot auf den Kopf- bzw. Fußbereich. caption ist die Überschrift der Tabelle. Mit insertRow() und deleteRow() kann man Zeilen einfügen oder löschen. Jede Zeile besitzt wiederum cells für ihre Zellen und die Methode insertCell(), um neue Zellen hinzuzufügen. Zellen haben außerdem colSpan und rowSpan, mit denen man festlegt, über wie viele Spalten oder Zeilen sie sich erstrecken.
Beispiel: document.querySelector("table").insertRow().insertCell().textContent = "Neu"; fügt eine neue Zeile mit einer Zelle hinzu.

ul:
Auch das Ul-Element hat kaum eigene Eigenschaften. Die Eigenschaft type für die Art der Aufzählungszeichen ist veraltet und wird heute über CSS gelöst. Man arbeitet hauptsächlich mit children, um auf die einzelnen Listeneinträge (li) zuzugreifen, und mit appendChild() oder removeChild(), um Einträge hinzuzufügen oder zu entfernen.
Beispiel: let li = document.createElement("li"); li.textContent = "Punkt"; document.querySelector("ul").appendChild(li); fügt einen neuen Listeneintrag hinzu.