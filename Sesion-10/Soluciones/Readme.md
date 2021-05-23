[`Programación con JavaScript`](../../Readme.md) > [`Sesión 10`](../Readme.md) > `Soluciones`

---

## Reto 1: Inflar un globo

```javascript
const p = document.querySelector("p");
let size;

function setSize(newSize) {
  size = newSize;
  p.style.fontSize = size + "px";
}

setSize(20);

function handleArrow(event) {
  if (event.key == "ArrowUp") {
    if (size > 80) {
      p.textContent = "💥";
      document.body.removeEventListener("keydown", handleArrow);
    } else {
      setSize(size * 1.1);
      event.preventDefault();
    }
  } else if (event.key == "ArrowDown") {
    setSize(size * 0.9);
    event.preventDefault();
  }
}

document.body.addEventListener("keydown", handleArrow);
```

---

## Reto 2: Modal

```javascript
const modal = document.getElementById("modal");

const button = document.getElementsByTagName('button')[0];
const modalImage = document.getElementById("modal-image");
const close = document.getElementsByClassName("close")[0];

button.addEventListener('click', function() {
  modal.style.display = "block";
  modalImage.src = 'https://picsum.photos/300/200';
})

close.addEventListener('click', function() {
  modal.style.display = "none";
})
```

---

## Reto 3: Navegando entre tabs

```javascript
function createTabs(node) {
  const tabs = Array.from(node.children).map(function (node) {
    const button = document.createElement("button")
    button.textContent = node.getAttribute("data-tabname")

    const tab = {
      node: node,
      button: button
    }

    button.addEventListener("click", function () {
      return selectTab(tab)
    })

    return tab;
  })

  const tabList = document.createElement("div")

  for (const tab of tabs) {
    tabList.appendChild(tab.button)
  }

  node.insertBefore(tabList, node.firstChild)

  function selectTab(selectedTab) {
    for (const tab of tabs) {
      const selected = tab === selectedTab
      tab.node.style.display = selected ? "" : "none"
      tab.button.style.color = selected ? "red" : ""
    }
  }

  selectTab(tabs[0])
}

createTabs(document.querySelector("#tab-panel"));
```
