## Prueba Técnica en Java (Parte 1): Manejo de Arrays

**Objetivo**:
Desarrollar un programa en Java que demuestre habilidades en el manejo de arrays.

Descripción de la Tarea:
Crear una aplicación de consola en Java que realice las siguientes operaciones utilizando arrays:

### Generación de Datos:

Generar un array de números enteros de tamaño N (donde N es un número proporcionado por el usuario).\
Llenar el array con números aleatorios (por ejemplo, entre 1 y 100).

### Operaciones con el Array:

Encontrar el número más grande y el más pequeño en el array.\
Calcular el promedio de los números en el array.\
Ordenar el array en orden ascendente y mostrar el resultado sin usar Stream.\
(Opcional) Implementar una búsqueda binaria para encontrar un número específico proporcionado por el usuario.

### Manejo de Excepciones:

Asegurarse de manejar posibles excepciones, como entradas inválidas del usuario.

### Entrega:

Código fuente de la aplicación en Java.\
Instrucciones para compilar y ejecutar el programa.\
Breve documentación que explique el enfoque utilizado y cualquier detalle relevante del código.

## Prueba técnica Java(parte 2) Cálculo y Ordenamiento:

Calcular la suma total del área de los paddocks para cada tipo de paddock (PaddockType). por ejemplo PaddockType 1 que son PALTOS la suma de sus areas es 56,259. \
Ordenar los tipos de paddocks (PaddockType) en orden descendente basándose en la suma total de su área plantada.\
Devolver un nuevo array que contenga los nombres de los PaddockType ordenados según el criterio anterior.

## No se permite el uso de stream solo manejo de arrays con `for` tradicional

**utiliza los json de abajo para generar los objetos**

**PaddockType**

```json
[
  { "id": 1, "name": "PALTOS" },
  { "id": 2, "name": "AVELLANOS" },
  { "id": 3, "name": "CEREZAS" },
  { "id": 4, "name": "NOGALES" }
]
```

**PaddockManager**

```json
[
  { "id": 1, "taxNumber": "132254524", "name": "JUAN TAPIA BURGOS" },
  { "id": 2, "taxNumber": "143618668", "name": "EFRAIN SOTO VERA" },
  { "id": 3, "taxNumber": "78903228", "name": "CARLOS PEREZ GONZALEZ" },
  { "id": 4, "taxNumber": "176812737", "name": "ANDRES VIÑALES CIENFUEGOS" },
  { "id": 5, "taxNumber": "216352696", "name": "OSCAR PEREZ ZUÑIGA" },
  { "id": 6, "taxNumber": "78684747", "name": "JOAQUIN ANDRADE SANDOVAL" }
]
```

**Paddocks**

```json
[
  {
    "paddockManagerId": 6,
    "farmId": 1,
    "paddockTypeId": 1,
    "harvestYear": 2019,
    "area": 1200
  },
  {
    "paddockManagerId": 1,
    "farmId": 3,
    "paddockTypeId": 4,
    "harvestYear": 2019,
    "area": 500
  },
  {
    "paddockManagerId": 5,
    "farmId": 3,
    "paddockTypeId": 2,
    "harvestYear": 2020,
    "area": 20000
  },
  {
    "paddockManagerId": 2,
    "farmId": 2,
    "paddockTypeId": 3,
    "harvestYear": 2021,
    "area": 8401
  },
  {
    "paddockManagerId": 3,
    "farmId": 1,
    "paddockTypeId": 1,
    "harvestYear": 2020,
    "area": 2877
  },
  {
    "paddockManagerId": 5,
    "farmId": 2,
    "paddockTypeId": 2,
    "harvestYear": 2017,
    "area": 15902
  },
  {
    "paddockManagerId": 3,
    "farmId": 3,
    "paddockTypeId": 2,
    "harvestYear": 2018,
    "area": 1736
  },
  {
    "paddockManagerId": 2,
    "farmId": 3,
    "paddockTypeId": 3,
    "harvestYear": 2020,
    "area": 2965
  },
  {
    "paddockManagerId": 4,
    "farmId": 3,
    "paddockTypeId": 4,
    "harvestYear": 2018,
    "area": 1651
  },
  {
    "paddockManagerId": 5,
    "farmId": 1,
    "paddockTypeId": 1,
    "harvestYear": 2018,
    "area": 700
  },
  {
    "paddockManagerId": 1,
    "farmId": 2,
    "paddockTypeId": 1,
    "harvestYear": 2019,
    "area": 7956
  },
  {
    "paddockManagerId": 5,
    "farmId": 3,
    "paddockTypeId": 2,
    "harvestYear": 2020,
    "area": 3745
  },
  {
    "paddockManagerId": 6,
    "farmId": 1,
    "paddockTypeId": 3,
    "harvestYear": 2021,
    "area": 11362
  },
  {
    "paddockManagerId": 2,
    "farmId": 3,
    "paddockTypeId": 3,
    "harvestYear": 2021,
    "area": 300
  },
  {
    "paddockManagerId": 3,
    "farmId": 2,
    "paddockTypeId": 2,
    "harvestYear": 2020,
    "area": 19188
  },
  {
    "paddockManagerId": 3,
    "farmId": 1,
    "paddockTypeId": 1,
    "harvestYear": 2019,
    "area": 17137
  },
  {
    "paddockManagerId": 4,
    "farmId": 3,
    "paddockTypeId": 2,
    "harvestYear": 2020,
    "area": 100
  },
  {
    "paddockManagerId": 2,
    "farmId": 1,
    "paddockTypeId": 3,
    "harvestYear": 2019,
    "area": 11845
  },
  {
    "paddockManagerId": 5,
    "farmId": 2,
    "paddockTypeId": 1,
    "harvestYear": 2018,
    "area": 15969
  },
  {
    "paddockManagerId": 1,
    "farmId": 3,
    "paddockTypeId": 1,
    "harvestYear": 2029,
    "area": 10420
  },
  {
    "paddockManagerId": 5,
    "farmId": 2,
    "paddockTypeId": 3,
    "harvestYear": 2010,
    "area": 3200
  },
  {
    "paddockManagerId": 6,
    "farmId": 1,
    "paddockTypeId": 2,
    "harvestYear": 2012,
    "area": 10587
  },
  {
    "paddockManagerId": 2,
    "farmId": 2,
    "paddockTypeId": 2,
    "harvestYear": 2018,
    "area": 16750
  }
]
```
