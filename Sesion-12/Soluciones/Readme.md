[`Programación con JavaScript`](../../Readme.md) > [`Sesión 12`](../Readme.md) > `Soluciones`

---

## Reto 1: Usuarios de Github

```javascript
const app = document.getElementById('app');

getGithubUsers()
  .then(function (data) {

    console.log(data);

    data.forEach(function (data) {
      app.appendChild(createCard(data));
    })
  })

function createCard(data) {
  const card = document.createElement('div');
  card.className = 'card';

  const name = document.createElement('h2');
  const nameText = document.createTextNode(data.login);

  name.appendChild(nameText)

  const link = document.createElement('a');
  const linkText = document.createTextNode('GitHub');

  link.appendChild(linkText);
  link.href = data.html_url;
  link.target = 'blank';
  link.className = 'button';

  const img = document.createElement('img');
  img.src = data.avatar_url;
  img.alt = data.login;

  card.appendChild(img);
  card.appendChild(name);
  card.appendChild(link);

  return card;
}

function getGithubUsers() {
  return fetch('https://api.github.com/users')
    .then(function (response) {
      return response.json();
    })
    .then(function (data) {
      return data.slice(0, 4)
    })
}
```

---

## Reto 2: Repositorios de Github

```javascript
const app = document.getElementById('app');

getGithubUsers()
  .then(function (data) {
    data.forEach(function (user) {
      return getUserRepositories(user.repos_url)
        .then(function (repos) {
          app.appendChild(createCard(user, repos));
        })
    })
  })

function createCard(data) {
  // Code from last challenge

  const reposList = createReposList(repos);

  card.appendChild(img);
  card.appendChild(name);
  card.appendChild(reposList);
  card.appendChild(link);

  return card;
}

function createReposList(repos) {
  const details = document.createElement('details');

  const summary = document.createElement('summary');
  const summaryText = document.createTextNode('Repositories:');
  summary.appendChild(summaryText);

  details.appendChild(summary);

  repos.forEach(function(repo) {
    const link = document.createElement('a');
    const linkText = document.createTextNode(repo.name);

    link.appendChild(linkText);
    link.href = repo.html_url;
    link.target = '_blank';
    link.className = 'button-repo';

    details.appendChild(link);
  })

  return details;
}

function getUserRepositories(url) {
  return fetch(url)
    .then(function (response) {
      return response.json();
    })
    .then(function (data) {
      return data.slice(0, 5)
    })
}
```

---

## Reto 3: Resultados Dinámicos

```javascript
function getGithubUsers() {
  return fetch('https://api.github.com/users')
    .then(function (response) {
      return response.json();
    })
    .then(function (data) {
      return shuffleArray(data).slice(0, 4)
    })
}

function getUserRepositories(url) {
  return fetch(url)
    .then(function (response) {
      return response.json();
    })
    .then(function (data) {
      return shuffleArray(data).slice(0, 5)
    })
}

function shuffleArray(array) {
  for(let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * i);
    [ array[i], array[j] ] = [ array[j], array[i] ];
  }
  return array
}
```
