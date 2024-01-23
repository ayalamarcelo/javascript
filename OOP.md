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
Y, claro, como hemos comentado antes, también podemos tener funciones. Cuando una función es parte de un objeto se le llama método.

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
