[`Programación con JavaScript`](../../Readme.md) > [`Sesión 09`](../Readme.md) > `Reto 02`

---

## Reto 2: Objetos anidados

### Objetivos

Extraer propiedades de un objeto anidado mediante asignación por destructuring.

#### Requisitos

`N/A`

#### Desarrollo

Dado el siguiente objeto:

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  links: {
    web: {
      blog: 'https://johndoe.com'
    }, 
    social: {
      facebook: 'https://facebook.com/john.doe',
      instagram: 'https://instagram.com/john.doe'
    } 
  }
};
```

Extraer las URLs de `facebook` e `instagram` y renombrar las variables por `fb` e `ig` respectivamente.

<details>
  <summary>Solución</summary>

```javascript
const { facebook: fb, instagram: ig } = person.links.social;
```

</details>
