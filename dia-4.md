# Ejercicios día 4

### Ejercicio 11
Crea una función llamada `max` que reciba un arreglo de números como argumento y retorne el número mayor.

**Nota:** No utilices el método `Math.max` de JavaScript.

```javascript
// escribe tu solución acá

// código de prueba
console.log(max([1, 2, 3, 4])) // 4
console.log(max([63, 85, 39, 24, 3])) // 85
```

### Ejercicio 12
Escribe una función llamada `hola` que reciba un argumento (una cadena de texto) y retorne "Hola " seguido del argumento y un signo de exclamación.

```javascript
// escribe la función hola acá

// código de prueba
console.log(hola("Pedro")) // "Hola Pedro!"
console.log(hola("Juan")) // "Hola Juan!"
console.log(hola("")) // "Hola !"
```

### Ejercicio 13
Escribe una función llamada `capitalizar` que reciba una cadena y capitalice cada palabra de la cadena.

**Nota:** puedes asumir que cada palabra está separada por espacio.

```javascript
// escribe la función acá

// código de prueba
console.log(capitalizar("pedro perez")) // "Pedro Perez"
console.log(capitalizar("make it real")) // "Make it Real"
```

### Ejercicio 14
Escribe una función llamada `promedio` que reciba un arreglo de números y retorne el promedio los elementos.

```javascript
// escribe la función acá

// código de prueba
console.log(promedio([1, 2, 3, 4])) // 2.5
console.log(promedio([7, 8, 9])) // 8
console.log(promedio([300, 100])) // 200
```

### Ejercicio 15
Escribe una función llamada `productosBaratos` que reciba un arreglo de objetos (que representan productos) y retorne un nuevo arreglo con los nombres de los productos cuyo precio esté entre 5 y 10:

```javascript
// escribe tu función acá

// código de prueba
let prods = [
  { nombre: "Arroz", precio: 5 },
  { nombre: "Pan", precio: 3 },
  { nombre: "Tomate", precio: 8 },
  { nombre: "Leche", precio: 15 }
];
console.log(productosBaratos(prods)); // ["Arroz", "Tomate"]
```
