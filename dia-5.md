# Evita estos errores en tu prueba técnica

Desde el 2014 hemos recibido miles de postulaciones de personas interesadas en estudiar en Make It Real. A continuación te compartimos los errores más comunes en las pruebas técnicas de nuestro proceso de admisión para aplicar al [Programa TOP](http://makeitreal.camp/top).

## No declarar una función

Normalmente se te pedirá que escribas una función que retorne algo. Un error común es enviar en tu prueba el código que escribirías en el cuerpo de la función sin incluir la definición de la función.

Por ejemplo. Si se te pidiera escribir una función llamada `suma` que retorne la sumatoria de `x` y `y`, dos valores que recibe como parámetro, una respuesta errada sería la siguiente:

```js
var x = prompt("Ingresa X")
var y = prompt("Ingresa Y")
console.log(x + y);
```

En la respuesta anterior no estás declarando una función de JavaScript como se pide en el ejercicio, estás escribiendo un programa que sólo funcionaría en el navegador (el prompt en el navegador abre una ventana para pedirle una entrada al usuario).

Una respuesta correcta sería:

```js
function suma(x, y) {
  return x + y;
}
```

En la respuesta anterior estás definiendo [^1] una función cuyo nombre es `suma` que recibe dos parámetros, `x` y `y`, y retorna desde el cuerpo de la función la suma de los valores asignados a cada una de estas variables.

Podrías haber escrito tu función con la sintaxis de funciones flecha, haber ignorado el  `;` al final de cada expresión, o haber usado paréntesis alrededor de la operación aritmética `(x + y)`. Lo anterior dependerá de los estilos que prefieras, pero lo **importante es que declares una función si se te está pidiendo**.

[^1]: Si somos estrictos semánticamente definir una función incluye el cuerpo de la función, mientras que el declarar la función no lo incluye, pero para el propósito de esta guia de refrencia, el significado de ambas palabras lo usaremos por igual. 

## Imprimir en vez de retornar

Un error común es imprimir un valor en vez de retornarlo. Normalmente se te pedirá que retornes un valor desde una función, no imprimirlo. Cuando retornas un valor desde la función, dicho valor podrías asignarlo a una variable y utilizarlo posteriormente en la ejecución de tu código. Cuando imprimes el valor con la función `console.log()` en vez de retornarlo, el valor retornado es `undefined`

Siguiendo con nuestro ejemplo de la función `suma`, la siguiente respuesta está errada:

```js
function suma(x, y) {
  console.log(x + y); // la función retorna undefined
}
```

El llamar la función anterior imprimirá en la consola el resultado de la suma pero retornará `undefined`, y lo que se pide en el ejercicio es que retorne el total de la sumatoria de los valores que pasas a la función como parámetros.

Si quisiéramos guardar el valor retornado por la función para utilizarlo posteriomente en nuestro código, pasaría lo siguiente:


```javascript
function suma(x, y) {
  console.log(x + y); // la función retorna undefined
};

const edad = suma(2, 4);
console.log(`Nayib tiene ${edad} años`); // Nayib tiene undefined años
```
En el ejemplo anterior estamos asignando el valor retornado por la función `suma` a la variable `edad` -línea 4 - , y posteriormente estamos interpolando la variable `edad` para que haga parte de la cadena de texto que estamos imprimiendo con la función `console.log()` - línea 6 - 

Nota la diferencia si retornamos el valor de la suma desde la función `suma`:

```js
function suma(x, y) {
  return (x + y);
};

const edad = suma(2, 4);
console.log(`Nayib tiene ${edad} años`); // Nayib tiene 6 años
```

Si te piden retornar un valor desde una función, recuerda que no es lo mismo que imprimir el valor con `console.log()` pues de hacerlo el valor retornado será `undefined`. 

## Quemar los valores y no usar los parámetros de la función

Uno de los propósitos de escribir funciones es poder reutilizar código. Si seguimos con el ejemplo anterior, no quemes los valores, usa los valores asignados a los parámetros que recibe tu función

```js
function suma(x, y) {
  return 2 + 4; // no estás usando el valor asignado a los parámetros sino retornando los que "quemaste"
}

console.log(suma(5, 5)) // retorna 6 y debería retornar 10
```

## Retornar el valor incorrecto

Otro error común es retornar el valor incorrecto. Supón que se te pide lo siguiente:

Escribe una función `agregar` que recibe como parámetro un arreglo y un número. La función debe retornar un nuevo arreglo cuyos elementos son aquellos elementos del arreglo y el número que pasas como parámetro a la función. 

Casos de prueba:

```js
console.log(agregar([1, 2, 3], 4)) // [1, 2, 3, 4]
console.log(agregar[2, 4, 6, 8], 10) // [2, 4, 6, 8, 10]
```

```js
function agregar(arr, num) {
  let resultado = [];

  for (let i = 0; i < arr.length; i++) {
    resultado.push(arr[i]);
  }

  resultado.push(num);

  return arr;
}

console.log(agregar([1, 2, 3], 4)) // [1, 2, 3] debería retornar [1, 2, 3, 4]
console.log(agregar([2, 4, 6, 8], 10)) // [2, 4, 6, 8] debería retornar [2, 4, 6, 8, 10]
```

En el caso anterior, se está retornando el arreglo original y no el nuevo arreglo que incluye como elemento el número que recibe la función como segundo argumento. Si te fijas `{ ... return arr; ...}` debería ser remplazado por `{... return resultado;}` - línea 9 -

```js
function agregar(arr, num) {
  let resultado = [];

  for (let i = 0; i < arr.length; i++) {
    resultado.push(arr[i]);
  }

  resultado.push(num);

  return resultado;
};

console.log(agregar([1, 2, 3], 4)) // [1, 2, 3, 4]
console.log(agregar([2, 4, 6, 8], 10)) // [2, 4, 6, 8, 10]
```

La función anterior puede escribirse de manera más corta con la nueva funcionalidad que nos da ES6 del *spread operator*, pero cualquiera de las dos formas es válida.

```js
function agregar(arr, num) {
  return [...arr, num];
};
```

Seguramnete en las entrevistas técnicas tu evaluador te pedirá que implementes un ciclo tradicional *for loop* para validar que sabes hacerlo. 

## Otros errores "tontos" que rompen tu código

* No cerrar un corchete o una llave. Se generará un error de systaxis. 

```js
function agregar(arr, num) {
  return [...arr, num // falta el corchete que cierra el arreglo.
};
```
* Olvidar los paréntesis al llamar la función.

```js
function hola() {
  return "Hola lola"
}

console.log(hola); // imprime [Function: hola], no estás llamando/invocando la función
console.log(hola()) // imprime el string retornafo por la funcion hola
```


* No imprimir el valor retornado por la función cuando estás validando los casos de prueba.

```js
function suma(x, y) {
  return (x + y);
};

suma(4, 6) 
// retornará el valor esperado pero no verás ningún resultado en la consola. 

console.log(suma(4, 6));
// la funcion retornará el valor esperado y se lo pasas a console.log() para poder validar que es el esperado
```

* Olvidar borrar los console.log() de prueba. 

```js
function suma(x, y) {
  console.log(x + y); // lo escribiste para probar y se te olvidó borrarlo. 
  return (x + y);
};
```

Hay más errores comunes que no hemos incluido. Si identificas más mientras haces tu prueba para el programa TOP, compártelos haciendo un Pull Request a este repositorio. 

Suerte en tu prueba y entrevista técnica. Esperamos verte pronto en el [Programa TOP](http://www.makeitreal.camp/top) de Make It Real.



Autor: [Nayib Abdalá](https://www.linkedin.com/in/nayibabdala/) | [Make It Real Camp](http://www.makeitreal.camp/top)
Esta guía hace parte del curso de preparación para el Programa TOP de Make It Real.
