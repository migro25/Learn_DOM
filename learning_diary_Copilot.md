Task 1:

1. Frage:
Document is a built-in object representing the current HTML page. 
Here, "document" finds the <h1> element, and textContent changes its text. It's provided by the browser -> not a JavaScript keyword. 
Usually it isn't available in node.js.

2. Frage:
You can use document to interact with the current webpage's html (the dom). 
examples:
-> // Read or change its text
console.log(button.textContent);
button.textContent = "Clicked!";

-> // Change its style or CSS classes
button.style.color = "blue";
button.classList.add("active");

Common tools include querySelector() -> find elements,
createElement() -> to make them,
addEventListener() -> to respond to events

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