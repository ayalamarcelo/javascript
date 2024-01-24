# Atajos para trabajar con objetos
Trabajar con objetos en muy común en js. En esta clase vamos a ver algunos atajos que nos permiten trabajar con ellos de forma más cómoda, tanto a la hora de crearlos como a la hora de recuperar sus propiedades.

## Atajo al crear un objeto
Imagina que quieres crear un objeto y que algunas de sus propiedades usen como valor algunas variables que ya tenemos.

```js
const name = 'Spidey'
const universe = 42

const spiderman = {
    name: name,
    universe: universe,
    powers: ['web', 'invisibility', 'spider-sense']
}
```
En este caso, podemos usar un atajo para crear el objeto. Si la propiedad y la variable tienen el mismo nombre, podemos omitir el valor y dejar solo el nombre de la propiedad.

```js
const name = 'Spidey'
const universe = 42

const spiderman = {
    name, // <- automáticamente asigna el valor de la variable name y universe
    universe,
    powers: ['web', 'invisibility', 'spider-sense']
}
```
Fijate que si tuvieramos `powers` fuera del objeto, podríamos crear el objeto en la misma línea:

```js
const name = 'Spidey'
const universe = 42
const powers = ['web', 'invisibility', 'spider-sense']

const spiderman = { name, universe, powers }
```
## Destructuración: el atajo al recuperar propiedades
En la anterior clase hemos visto que para recuperar una propiedade de un objeto podemos usar la notación de corchetes o la notación de punto:

```js
const spiderman = {
    name: 'Spidey',
    universe: 42,
    powers: ['web', 'invisibility', 'spider-sense']
} 

console.log(spiderman['name']) // Spidey
console.log(spiderman.name) // Spidey
```
A veces queremos recuperar el valor de la propiedad y guardarlo en una variable, para usarlo más adelante. Haríamos algo así:

```js
const universe = spiderman.universe
console.log(universe) // 42

const powers = spiderman['powers'][1]
console.log(powers) // 'invisibility'
```
> spiderman['powers'][1] de nuevo puede parecer un poco confuso, pero hay que separarlo en partes. `spiderman` es el objeto. Accedemos a la propiedad `powers` y como es un array, podemos acceder a su segundo elemento con [1]. Y ahí está el valor que queremos: `invisibility`.

A la hora de acceder a las propiedades existe un atajo llamado desestructuración (o destructuring) muy interesante que nos permite recuperar el valor de una propiedad y guardalo en una variable de una.
Lo importante es que tengamos en cuenta que la variable que se creará tendrá el mismo nombre que la propiedad que estamos recuperando.

```js
const { universe } = spiderman
console.log(universe) // 42
```

Además, puedes recuperar tantas propiedades como quieras, separándolas por comas.

```js
const { universe, name, powers } = spiderman
console.log(universe) // 42
console.log(name) // 'Spidey'
console.log(powers) // ['web', 'invisibility', 'spider-sense']
```
## Renombrar variables y valor por defecto
Si quieres que la variable que se crea tenga un nombre diferente al de la propiedad, puedes hacerlo así:

```js
const { universe: universeNumber } = spiderman
console.log(universeNumber) // 42
```
Lo que estamos haciendo es recuperar la propiedad `universe` pero crear la constante con el nombre `universeNumber`.

Si la propiedad no existe, podemos asignarle un valor por defecto:

```js
const { name, isAvenger = false } = spiderman

console.log(name) // 'Spidey'
console.log(isAvenger) // false
```
El objeto que hemos creado antes no tenía la propiedad `isAvenger`, pero al recuperarla le hemos asignado un valor por defecto de `false`. si no le hubiéramos asignado un valor por defecto, la variable `isAvenger` sería `undefined`.

Asi que recuperamos una propiedad que no existe, la variable que se creará tendrá el valor por defecto que le hayamos asignado. Y lo hacemos usando el operador `=`.

> Esto es muy útil, por ejemplo, para recuperar opciones o configuración del usuario que quizás no ha definido todos los valores pero tenemos claro qué comportamiento queremos que tenga nuestra aplicación por defecto.

## Objetos anidados y atajo
Ya sabemos que podemos tener un objeto dentro de un objeto:

```js
const spiderman = {
    name: 'Spidey',
    universe: 42,
    powers: ['web', 'invisibility', 'spider-sense'],
    partner: {
        name: 'Mary Jane',
        universe: 42,
        powers: ['red hair', 'blue eyes']
    }
}
```
Para acceder a las propiedades de un objeto anidado, podemos usar la notación de corchetes o la notación de punto:

```js
console.log(spiderman.partner.name) // 'Mary Jane'
console.log(spiderman['partner']['name']) // 'Mary Jane'
```
Si queremos recuperar la propiedad `name` del objeto `partner` y guardarla en una variable, podemos hacerlo así:

```js
const { partner } = spiderman
const { name } = partner
console.log(name) // 'Mary Jane'
```
Pero también podemos hacerlo en una sola línea:

```js
const { partner: { name } } = spiderman
console.log(name) // 'Mary Jane'
```
Lo que estamos haciendo es: del objeto `spiderman` extrae la propiedad `partner`, y de esta, extrae la propiedad `name`. Como resultado sólo crearemos la variable `name` con el valor `Mary Jane`.