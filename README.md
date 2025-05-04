# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript and DOM Manipulation</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1 id="heading">JavaScript and DOM Manipulation</h1>
    </header>
    <main>
        <section>
            <p id="paragraph">This is a paragraph of text.</p>
            <button id="change-text-button">Change Text</button>
        </section>
        <section>
            <p id="style-demo">Style Demo</p>
            <button id="change-style-button">Change Style</button>
        </section>
        <section>
            <ul id="list">
                <li>Item 1</li>
                <li>Item 2</li>
            </ul>
            <button id="add-item-button">Add Item</button>
            <button id="remove-item-button">Remove Item</button>
        </section>
    </main>
    <script src="script.js"></script>
</body>
</html>
```

style.css
```
body {
    font-family: Arial, sans-serif;
}

#style-demo {
    font-size: 18px;
    color: #333;
}
```

script.js
```
// Change text content dynamically
document.getElementById('change-text-button').addEventListener('click', () => {
    document.getElementById('paragraph').textContent = 'The text has been changed!';
});

// Modify CSS styles via JavaScript
document.getElementById('change-style-button').addEventListener('click', () => {
    const styleDemo = document.getElementById('style-demo');
    styleDemo.style.fontSize = '24px';
    styleDemo.style.color = 'blue';
});

// Add or remove an element when a button is clicked
document.getElementById('add-item-button').addEventListener('click', () => {
    const list = document.getElementById('list');
    const newItem = document.createElement('li');
    newItem.textContent = `Item ${list.children.length + 1}`;
    list.appendChild(newItem);
});

document.getElementById('remove-item-button').addEventListener('click', () => {
    const list = document.getElementById('list');
    if (list.children.length > 0) {
        list.removeChild(list.lastChild);
    }
});
