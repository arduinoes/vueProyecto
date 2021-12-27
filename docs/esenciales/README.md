---
sidebar: auto
---
# Esenciales

## Base HTML

Bootstrap [CDN CSS](https://getbootstrap.com/docs/5.1/getting-started/introduction/)
Vue.js [CDN](https://v3.vuejs.org/guide/installation.html#vue-devtools)

#### Archivo HTML

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Vue</title>
    <!-- CDN Boostrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <!-- CDN Vue.js -->
    <script src="https://unpkg.com/vue@next"></script>
  </head>
  <body>
    <div id="app">
      
    </div>
    <!-- Importa App -->
    <script src="./main.js"></script>
    <!-- Monta Vue.js -->
    <script>
      const mountedApp = app.mount('#app')
    </script>
  </body>
</html>
```

#### Archivo JavaScript

```js
const app = Vue.createApp({
  data() {
    return {

    };
  },
});
```
## Bootstrap

[CARD](https://getbootstrap.com/docs/5.1/components/card/)

```html
<div class="d-flex justify-content-center mt-5">

    <div class="card" style="width: 18rem;">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
    </div>

</div>
```
## Directivas
### Mustache => Datos
```html
<h5 class="card-title">{{ nombre }}</h5>
```
```js
nombre: "Gamora",
```
### v-bind : => Atibutos
```html
<img :src="image" class="card-img-top" alt="Vue esenciales">
```
```js
image: "./assets/images/Gamora.jpeg",
```
### v-if / else => Condicionales

```html
<p v-if="cantidad > 10 " class="card-text">En stock</p>
<p v-else-if="cantidad <= 10 && cantidad > 0" class="card-text">Ultimas unidades</p>
<p v-else="cantidad > 10 " class="card-text">Sin stock</p>
```
```js
cantidad: 0,
```

### v-for => Bucles
```html
<div v-for="heroe in heroes" :key="heroe.id" class="card mt-5" style="width: 18rem;">
```
```html
 <img :src="heroe.image" class="card-img-top" alt="Vue esenciales">
```
```html
  <h5 class="card-title">{{ heroe.nombre }}</h5>
```
```js
 heroes: [
        { id: 01, nombre: "Gamora", image: "./assets/images/Gamora.jpeg"},
        { id: 02, nombre: "Groot", image: "./assets/images/Groot.jpeg"},
        { id: 03, nombre: "Rocket", image: "./assets/images/Rocket.jpeg"},
        { id: 04, nombre: "StarLord", image: "./assets/images/StarLord.jpeg"}
      ]
```
### v-on => Manejando de eventos
```html
<h5>Cantidad: {{ cantidad }}</h5>
```
```html
<button @click.prevent="incrementar" class="btn btn-primary">Incrementar</button>
```
```js
  methods: {
    incrementar () {
      this.cantidad ++
    }
  }
```