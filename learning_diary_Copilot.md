Task 1:

1. Frage:
Das Document ist ein eingebautes Objekt, das die aktuelle HTML-Seite repräsentiert.
Hier findet „document“ das <h1>-Element, und textContent ändert dessen Text. Es wird vom Browser bereitgestellt -> ist also kein JavaScript-Schlüsselwort.
Normalerweise ist es in Node.js nicht verfügbar.

2. Frage:
Man kann document verwenden, um mit dem HTML der aktuellen Webseite (dem DOM) zu interagieren.
Beispiele:
-> // Text lesen oder ändern
console.log(button.textContent);
button.textContent = "Clicked!";

-> // Stil oder CSS-Klassen ändern
button.style.color = "blue";
button.classList.add("active");

Häufig verwendete Werkzeuge sind querySelector() -> zum Finden von Elementen,
createElement() -> zum Erstellen von Elementen,
addEventListener() -> um auf Ereignisse (Events) zu reagieren

Task 2:

1. Frage: 
Mit dem Befehl: ""const myList = document.getElementById("myList");" sucht man in der HTML-Seite nach dem Element mit id="myList" - das ist hier die gesamt <ul>-Liste. Dieses Element wird in der JavaScript-Variablen myList gespeichert.

Mit den Befehlen von CoPilot:
console.log(myList.textContent); // zeigt den Text der ganzen Liste

const items = myList.querySelectorAll("li"); // findet alle Listeneinträge
console.log(items[0].textContent); // zeigt "Item 1"

Ein Hinweis bekam ich noch: "myList ist nicht automatisch ein JavaScript-Array. Es ist eine Referenz auf das HTML-Element. Die Liste steht in deiner index.html."

2. Frage:
Zuerst wählt man die Liste mit document.getElementById("myList") aus. Danach kann man ihre Einträge mit JavaScript verändern.

Der Code dafür:
const myList = document.getElementById("myList");

myList.querySelector("li").textContent = "Ein neuer erster Eintrag";

const newItem = document.createElement("li");
newItem.textContent = "Item 4";
myList.append(newItem);

querySelector("li") findet den ersten Listeneintrag. Mit textContent ändert man seinen Text. document.createElement("li") erstellt einen neuen Listeneintrag, und append() fügt ihn am Ende der Liste hinzu.

Diese Änderungen sieht man auf der Webseite, solange sie läuft. Damit sie dauerhaft in der HTML-Datei stehen, muss man die <li>-Elemente direkt in der HTML-Datei bearbeiten.

Man kann ein Element anhand seiner id finden, auf seine Listeneinträge zugreifen und diese verändern oder neue hinzufügen.