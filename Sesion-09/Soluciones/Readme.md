[`Programación con JavaScript`](../../Readme.md) > [`Sesión 09`](../Readme.md) > `Soluciones`

---

## Reto 1: Reemplazar imágenes

```javascript
const images = document.body.getElementsByTagName("img");

for (let i = images.length - 1; i >= 0; i--) {
  const image = images[i];
  if (image.alt) {
    const text = document.createTextNode(image.alt);
    image.parentNode.replaceChild(text, image);
  }
}
```

---

## Reto 2: Crear una tabla

```javascript
function buildTable(data) {
  const table = document.createElement("table");

  const fields = Object.keys(data[0]);
  const headRow = document.createElement("tr");
  fields.forEach(function(field) {
    const headCell = document.createElement("th");
    headCell.appendChild(document.createTextNode(field));
    headRow.appendChild(headCell);
  });
  table.appendChild(headRow);

  data.forEach(function(object) {
    const row = document.createElement("tr");
    fields.forEach(function(field) {
      const cell = document.createElement("td");
      cell.appendChild(document.createTextNode(object[field]));
      if (typeof object[field] == "number") {
        cell.style.textAlign = "right";
      }
      row.appendChild(cell);
    });
    table.appendChild(row);
  });

  return table;
}

document.getElementById("mountains")
   .appendChild(buildTable(data));
```

