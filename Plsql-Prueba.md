## Prueba Técnica: Creación de un Procedimiento Almacenado en PL/SQL

### Enunciado:

Dado el alto tráfico de los últimos años en el país, una empresa pionera en el desarrollo de tecnologías ha decidido instalar sensores en los semáforos de todo el país, con el fin de registrar el tráfico que diariamente transita por ellos. Los datos se almacenan en una serie de tablas; por un lado, se tiene la información de los dueños de los vehículos en la tabla `owners`, la información de los vehículos en la tabla `car_metadata` y la tabla coordinates que contiene la ubicación de todos los semáforos. La información que envían los sensores instalados en cada semáforo se almacena en la tabla `car_events`. Se nos pide cruzar esta información para obtener reportes precisos sobre el tráfico, estos reportes serán consultados de forma asíncrona por cual deberán ser almacenados en la tabla `REP_CARS` el id de la tabla queda a tu conveniencia si desea utilizar UUID, secuenciales u otra forma de identificación.

### Objetivo:

Desarrollar un procedimiento almacenado en PL/SQL que extraiga y procese datos de eventos de tráfico basados en un rango de fechas específico. El procedimiento cruzará información entre varias tablas relacionadas con los eventos de tráfico, propietarios de vehículos, metadatos de vehículos y coordenadas de semáforos.

### Requisitos:

Procedimiento Almacenado:

**Nombre del procedimiento:** obtener_eventos_por_fecha.

#### Parámetros de Entrada:

- p_fecha_inicio (DATE): Fecha de inicio para filtrar los eventos.
- p_fecha_fin (DATE): Fecha de fin para filtrar los eventos.

### Lógica del Procedimiento:

Realizar consultas a las tablas **car_events**, **owners**, **car_metadata** y **coordinates**.

Filtrar los eventos en car_events para incluir solo aquellos dentro del rango de fechas especificado por los parámetros.

Cruzar los datos de car_events con:
owners para identificar al propietario del vehículo en el momento del evento.
car_metadata para obtener detalles del vehículo como motor, tipo de combustible y tipo de vehículo.
coordinates para obtener la ubicación del semáforo (ciudad y calle).
Insertar los resultados en la tabla **REP_CARS**, con los campos: owner_name, plate, engine, fuel_type, car_type, date_at, date_time, city, street.

### Manejo de Excepciones y Validaciones:

Incluir un adecuado manejo de excepciones para asegurar la robustez del procedimiento.

### Pruebas y Validación del Procedimiento:

Realizar pruebas para verificar que el procedimiento funciona correctamente con diferentes rangos de fechas.
Asegurar que los datos insertados en REP_CARS sean coherentes y precisos.

### Evaluación:

Se evaluará la capacidad para escribir un procedimiento almacenado eficiente y bien estructurado en PL/SQL.\
(Nice to have) \
La precisión y la coherencia de los datos resultantes serán puntos clave en la evaluación.\
Se valorará el uso de buenas prácticas de programación, incluyendo la claridad del código, el manejo de excepciones

### Entrega:

Entregar el script del procedimiento almacenado junto con un conjunto de instrucciones para su prueba y validación.
Se espera también un breve explicación del enfoque utilizado y cualquier consideración relevante sobre el diseño del procedimiento.

```sql
CREATE TABLE owners (
    id NUMBER NOT NULL,
    placa VARCHAR2(10) NOT NULL,
    fecha_inicio DATE NOT NULL,
    fecha_fin DATE NOT NULL,
    nombre VARCHAR2(100) NOT NULL
);
```

```sql
CREATE TABLE car_events (
    placa VARCHAR2(10) NOT NULL,
    fecha DATE NOT NULL,
    fecha_hora TIMESTAMP NOT NULL,
    semaforo_id NUMBER NOT NULL
);
```

```sql
CREATE TABLE car_metadata (
    owner_id NUMBER NOT NULL,
    color VARCHAR2(50),
    motor VARCHAR2(50),
    combustible VARCHAR2(50),
    tipo VARCHAR2(50)
);
```

```sql
CREATE TABLE coordinates (
    id NUMBER NOT NULL,
    latitud NUMBER(9,6),
    longitud NUMBER(9,6),
    ciudad VARCHAR2(100),
    calle VARCHAR2(100),
    fecha_inicio DATE NOT NULL,
    fecha_fin DATE NOT NULL
);
```

```sql
CREATE TABLE REP_CARS (
    id NUMBER(10)    NOT NULL.
    owner_name VARCHAR2(100),
    plate VARCHAR2(10),
    engine VARCHAR2(50),
    fuelType VARCHAR2(50),
    car_type VARCHAR2(50),
    date_at DATE,
    date_time TIMESTAMP,
    city VARCHAR2(100),
    street VARCHAR2(100)
);
-- si es necesario modifica el id de la tabla por UUID o lo que sea conveniente para identificarlo
```
