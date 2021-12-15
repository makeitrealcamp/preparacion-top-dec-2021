# Ejercicios día 3

## Ejercicio 6

Crear un programa que calcule la división de dos números. En caso de que el divisor sea cero mostrar un mensaje de error.

## Ejercicio 7

Crear un programa para calcular el salario de una persona con base en el número de horas trabajadas y el valor de la hora. Si la persona trabaja más de 40 horas, las horas extras deben pagarse con un incremento del 50% sobre el valor de la hora normal.

Mostrar el salario total y cuánto ganó por horas extras.

Ejemplo:

Entradas:
```
Total Horas 45
Valor Hora 2000
```

Salidas:
```
Total Ordinario 80000 (40 horas * $2000)
Horas Extra 5
Recargo por horas extra 3000 ($2000 * 1.5)
Total recargo por horas extra $15000
Total devengado $95000
```

## Ejercicio 8
Se tienen 2 arreglos paralelos con los siguientes valores:

```
asistentes = ["Gina", "Juan", "Luz", "Michael"];
asistencia = [true, true, false, true];
```

Se debe recorrer el arreglo en un ciclo e informar si cada persona asistió o no a la sesión de Make It Real de la siguiente forma:

```
“Gina asistió”
“Juan asistió”
“Luz no asistió”
“Michael asistió”
```

## Ejercicio 9

Crea una variable llamada `pedro` de tipo objeto literal con las siguientes llaves y valores:

- `nombre` - "Pedro Perez"
- `edad` - 30
- `activo` - true
- `hobbies` - un arreglo con los siguientes elementos: "programar", "squash", "piano".

Ahora haz lo siguiente:

1. Imprime en consola el valor de la llave `edad`.
2. Agrega una propiedad con llave `estatura` y valor `1.8`.
3. Elimina la propiedad con llave `activo`.
4. Recorre todas las propiedades e imprímelas en consola (una línea por propiedad y separando la llave y el valor con dos puntos `:`).

El resultado en consola debería ser parecido al siguiente (puede que las propiedades no salgan en el mismo orden):

```
30
nombre: "Pedro Perez"
edad: 30
hobbies: ["programar", "squash", "piano"]
estatura: 1.8
```


## Ejercicio 10
Obtener la edad de las personas que hablen inglés (EN) de un arreglo de 5 objetos Persona. Cada elemento del arreglo tiene la siguiente estructura:
```
[{
  nombre: "Juana",
  sexo: "F",
  edad: 30,
  idiomas: ["EN","ES"]
},{
  nombre: "Mario",
  sexo: "M",
  edad: 20,
  idiomas: ["ES"]
},{
  nombre: "Carla",
  sexo: "F",
  edad: 31,
  idiomas: ["EN"]
}, ...]
```

Respuesta:
```
Juana, Carla
```


