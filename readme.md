# BD DOCKER - Prueba Tecnica

Este proyecto configura un contenedor de MySQL utilizando **Docker Compose** para poder correr la prueba tecnica. Proporciona una base de datos predefinida llamada `transportept`.

---

## 📋 Requisitos Previos

1. **Docker** y **Docker Compose** instalados en tu máquina. Si no los tienes:
   - [Instalar Docker](https://docs.docker.com/get-docker/)
   - [Instalar Docker Compose](https://docs.docker.com/compose/install/)

2. Verifica si tienes un archivo `schemas` en tu directorio local, ya que este será mapeado al contenedor para almacenar la base de datos. En caso de no tenerlo se creara automaticamente.

---

## 📦 Contenido del Docker Compose

- **Servicio `db`**
  - Imagen base: `mysql`
  - Nombre del contenedor: `BDPRUEBATECNICA`
  - Puerto expuesto: `3306`
  - Variables de entorno:
    - `MYSQL_ROOT_PASSWORD`: `pruebatecnica`
    - `MYSQL_DATABASE`: `transportept`
  - Volumen:
    - `./schemas` mapeado a `/var/lib/mysql`

---

## 🚀 Cómo ejecutar el proyecto

1. **Clona o descarga este repositorio.**
2. Asegúrate de estar en la misma carpeta donde está el archivo `docker-compose.yml`.
3. Ejecuta el siguiente comando para iniciar los servicios:

   ```bash
   docker-compose up -d
   ```

   Esto hará que el contenedor de MySQL se ejecute en segundo plano.

4. **Verifica que el contenedor está corriendo:**

   ```bash
   docker ps
   ```

   Deberías ver un contenedor con el nombre `BDPRUEBATECNICA`.

---

## 🛑 Cómo detener los servicios

1. Para detener el contenedor sin eliminarlo, usa:

   ```bash
   docker-compose stop
   ```

2. Si deseas detener y eliminar los contenedores creados, usa:

   ```bash
   docker-compose down
   ```

---

## 🧪 Notas adicionales

- Puedes conectarte a la base de datos usando herramientas como MySQL Workbench:
  - **Host**: `localhost`
  - **Puerto**: `3306`
  - **Usuario**: `root`
  - **Contraseña**: `pruebatecnica`
  - **Base de datos predeterminada**: `transportept`

- **Persistencia de datos**: La base de datos está configurada para persistir los datos en el directorio local `./schemas`. Si eliminas este directorio, perderás los datos.
