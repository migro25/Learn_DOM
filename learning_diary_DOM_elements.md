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

Das ergibt `"small"` oder `"large"`. Wenn keiner ausgewählt ist, ergibt es `undefined`.

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

Damit greifst du auf das Formular zu und liest den eingegebenen Namen aus.