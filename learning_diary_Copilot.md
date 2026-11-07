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