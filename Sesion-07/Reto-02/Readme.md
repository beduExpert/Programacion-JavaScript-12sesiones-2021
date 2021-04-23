[`Programación con JavaScript`](../../Readme.md) > [`Sesión 07`](../Readme.md) > `Reto 02`

---

## Reto 2: Crear una tabla

### Objetivos

Crear una tabla en el DOM a partir de un arreglo de objetos.

#### Requisitos

Partir del siguiente documento HTML:

```html
<html>
  <head>
    <meta charset="utf8" />
    <title>Reto 2: Crear una tabla</title>
  </head>
  <body>
    <h1>Mountains</h1>

    <div id="mountains"></div>

    <script>
      var data = [
        {name: "Kilimanjaro", height: 5895, place: "Tanzania"},
        {name: "Everest", height: 8848, place: "Nepal"},
        {name: "Mount Fuji", height: 3776, place: "Japan"},
        {name: "Vaalserberg", height: 323, place: "Netherlands"},
        {name: "Denali", height: 6168, place: "United States"},
        {name: "Popocatepetl", height: 5465, place: "Mexico"},
        {name: "Mont Blanc", height: 4808, place: "Italy/France"}
      ];
      // Code goes here
    </script>
  </body>
</html>
```

#### Desarrollo

En HTML podemos construir tablas usando etiquetas como las siguientes:

```HTML
<table>
  <tr>
    <th>Name</th>
    <th>Height</th>
    <th>Place</th>
  </tr>
  <tr>
    <td>Kilimanjaro</td>
    <td>5895</td>
    <td>Tanzania</td>
  </tr>
</table>
```

La etiqueta `<table>` define la tabla, cada fila está compuesta por la etiqueta `<tr>`.
Dentro de cada fila podemos crear celdas como headers `<th>` o celdas regulares `<td>`.

Crear una tabla a partir de la información proporcionada por `data`, un arreglo
de objetos con las propiedades `name`, `height` y `place`. La tabla debe contener
una columna por cada propiedad, y una fila por cada objeto. Adicionalmente debe
contener una fila con headers `<th>` listando el nombre de cada columna, el cual
corresponde a las propiedades del objeto.

Alinear hacia la derecha las celdas que contengan valores numéricos asignando a la
propiedad `style.textAlign` el valor `right`.

<details>
  <summary>Solución</summary>

```javascript
function buildTable(data) {
  var table = document.createElement("table");

  var fields = Object.keys(data[0]);
  var headRow = document.createElement("tr");
  fields.forEach(function(field) {
    var headCell = document.createElement("th");
    headCell.appendChild(document.createTextNode(field));
    headRow.appendChild(headCell);
  });
  table.appendChild(headRow);

  data.forEach(function(object) {
    var row = document.createElement("tr");
    fields.forEach(function(field) {
      var cell = document.createElement("td");
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

</details>
