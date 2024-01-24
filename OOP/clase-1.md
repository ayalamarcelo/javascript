# Programación orientada a objetos
Los objetos en js son una colección de propiedades y métodos que definen un elemento a través de una clave y un valor.
Por ejemplo, si pensamos en una persona, podemos definir sus propiedades como su nombre, su edad, su altura, su peso, etc. Y sus métodos como caminar, correr, saltar, etc.

## Declaración y asignación de objetos
Para declarar un objeto usamos las llaves `{}` y dentro las propiedades y métodos separados por comas `,`. Cada propiedad o método se define con una clave y un valor separados por dos puntos `:`.
Por ejemplo, vamos a crear un objeto que represente a una persona:


```js

const persona = {
    name: 'Dani',
    age: 30,
    isWorking: true
}
```
Las propiedades y métodos de un objeto pueden ser de cualquier tipo de js, incluso otro objetos o arrays.

```js

const persona = {
    name: 'Dani',
    age: 30,
    isWorking: true,
    family: ['Miguel', 'Maria'], // array
    address: { // otro objeto
     street: 'Calle de la piruleta',
     number: 13,
     city: 'Barcelona'
    }
}
```
Y, claro, como hemos comentado antes, también podemos tener funciones. Cuando una función es parte de un objeto se le llama `método`.

```js

const persona = {
    name: 'Dani',
    age: 30,
    isWorking: true,
    family: ['Miguel', 'Maria'],
    address: {
        street: 'Calle de la pirueta',
        number: 13,
        city: 'Barcelona'
    },
    walk: function () { // <- método
    console.log('Estoy caminando') 
    }
}
```
## Acceder a propiedades y métodos de un objeto
Para acceder a la propiedad y métodos de un objeto usamos le punto `.` y el nombre de la propiedad o método.

```js

const persona = { name: 'Dani' }
console.log(persona.name) // Dani
```
Si intentamos acceder a una propiedad o método que no existe, nos devolverá `undefined`.

```js

const persona = { name: 'Dani' }
console.log(persona.fullName) // -> undefined
```
Puedes usar variables para acceder a las propiedades y métodos de un objeto. Para ello, tienes que usar la notificación por corchetes `[]`.

```js

const persona = { name: 'Dani' }
let property = 'name'

console.log(persona[property]) // -> Dani
```
También necesitas usar los corchetes si la clave de la propiedad o método tiene espacios o caracteres especiales.

```js

const persona = { 'Full name': 'Dani' }
console.log(persona['full name']) // -> Dani

// no puedes hacer esto
// persona.full name
```
>[!Note]
> Siempre que puedas, evita usar espacios o caracteres especiales en las claves de las propiedades y métodos de un objeto. Aunque se puede, es más complicado de leer y de escribir.

Igual que las propiedades, puedes acceder a los métodos de un objeto usando cualquiera de las dos formas anteriormente comentadas:

```js
const persona = {
    name: 'Dani',
    walk: function () {
        console.log('Estoy caminando')
    }
}

persona.walk() // -> estoy caminando

let method = 'walk'
persona[method]() // -> estoy caminando
```
> persona[method]() parece un poco raro, pero si lo separas parte por parte, verás que tiene sentido. persona es el objeto. Accedemos a la propiedad **method** del objeto **persona** con **persona[method]**. Y, finalmente, ejecutamos la función con `persona[method]()`. Es decir, estamos ejecutando `persona.walk()`.

## Añadir y modificar propiedades de un objeto
igual que podemos acceder a las propiedades de un objeto, podemos añadir nuevas propiedades o modificar las existentes.

```js

const persona = { name: 'Dani' }
persona.age = 30
console.log(persona) // -> { name: 'Dani', age: 30 }
```
En el código estamos modificando el objeto `persona` añadiendo la propiedad `age` con el valor 30.

> Fíjate que, al igual que en los Arrays, podemos añadir propiedades a un objeto aunque sea una constante. Esto es porque no estamos reasignando la variable persona, si no que estamos modificando una propiedad interna del objeto.

## Eliminar propiedades de un objeto
Para eliminar una propiedad de in objeto usamos la palabra reservada `delete`.

```js
const persona = { name: 'Dani', age: 18 }
delete persona.age
console.log(persona) // -> { name: 'Dani'}
```

### Ejericicio práctico

Tenemos una función que recibe dos parámetros. name y subs. Haz que la función devuelva un objeto con la siguiente información:

    name con el valor del parámetro name
    subscribers con el valor del parámetro subs
    hash, con el valor de la longitud del string name multiplicado por el parámetro subs
    Un método getStatus que devuelva el texto El canal de <name> tiene <subs> suscriptores. Por ejemplo, para name = 'Dani' y subs = 100, el método getStatus devolvería El canal de Dani tiene 100 suscriptores.

¡Ojo! El método getStatus debe devolver el texto, NO imprimirlo por consola.