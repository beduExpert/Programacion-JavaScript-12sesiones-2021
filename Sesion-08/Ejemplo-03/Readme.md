[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Ejemplo 0`

---

## Ejemplo 3: Webpack y Babel

### Objetivo

Instalar y configurar babel junto con webpack

#### Requisitos

Continuar con el código del reto 1

#### Desarrollo

Vamos a empezar instalando las siguientes librerías:

```text
npm install --save-dev @babel/core @babel/preset-env babel-loader
```

- **@babel/core:** Esta es la librería principal. [Documentación](https://babeljs.io/docs/en/babel-core)
- **@babel/preset-env:** Preset con las características más recientes de
  JavaScript. [Documentación](https://babeljs.io/docs/en/babel-preset-env)
- **babel-loader:** Loader de webpack. [Documentación](https://webpack.js.org/loaders/babel-loader/)

En nuestro archivo de configuración de webpack agregamos el nuevo loader.

```javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  plugins: [
    new HtmlWebpackPlugin({
      filename: 'index.html',
      template: './src/index.html'
    })
  ],
  module: {
    rules: [
      { test: /\.css$/, use: ['style-loader', 'css-loader'] },
      {
        test: /\.m?js$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ['@babel/preset-env']
          }
        }
      },
    ]
  },
  devServer: {
    contentBase: path.resolve(__dirname, 'dist')
  }
}
```

Con esto, cada vez que webpack encuentre un archivo `.js` lo pasará por babel primero antes de hacer el bundle. Lo
último que nos falta es crear un nuevo archivo en la raíz `babel.config.json`, aquí es donde configuramos babel y le
indicamos el preset que debe usar.

```json
{
  "presets": ["@babel/preset-env"]
}
```

La estructura final que tenemos es la siguiente:

```
demo
|- /dist
|- /node_modules
|- /src
|    |- index.html
|    |- /css
|       |- styles.css
|    |- /js
|       |- index.js
|- babel.config.json
|- package.json
|- package-lock.json
|- webpack.config.js
```
