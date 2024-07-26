# Banco Solar API

## Descripción

Banco Solar es una API simple para la gestión de usuarios y transferencias en una base de datos PostgreSQL. Esta API permite agregar, editar, eliminar usuarios y registrar transferencias entre ellos.

## Requisitos

- **Node.js**
- **PostgreSQL**
## Configuración de la Base de Datos

1. **Crear la Base de Datos**

 ```sql
   CREATE DATABASE bancosolar;


   CREATE TABLE usuarios (
  id SERIAL PRIMARY KEY,
  nombre VARCHAR(255) NOT NULL,
  balance NUMERIC NOT NULL
);

CREATE TABLE transferencias (
  id SERIAL PRIMARY KEY,
  emisor INTEGER REFERENCES usuarios(id),
  receptor INTEGER REFERENCES usuarios(id),
  monto NUMERIC NOT NULL,
  fecha TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```
```js
## Datos de conexión

const pool = new Pool({
  user: "postgres",
  host: "localhost",
  password: "1234",  // Cambia esta línea si tu contraseña es diferente
  database: "bancosolar",
  port: 5432,
});

```
