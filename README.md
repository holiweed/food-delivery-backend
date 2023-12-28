<div align="center">
  <h1>Nestjs - Food Delivery Backend</h1>

![image](https://img.shields.io/badge/nestjs-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![image](https://img.shields.io/badge/GraphQl-E10098?style=for-the-badge&logo=graphql&logoColor=white)
![image](https://img.shields.io/badge/Handlebars.js-f0772b?style=for-the-badge&logo=handlebarsdotjs&logoColor=black)
![image](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![image](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![image](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

<p>Aplicación de comida a domicilio basada en el concepto de uber, rappi, etc... En el que podrás registrarte como cliente, propietario o repartidor y dependiendo de tu perfil podrás dar de alta tu restaurante para la venta de comida, ayudar a entregar pedidos y pedir lo que más te guste.</p>

</div>

### Vista previa

![](./.readme-static/app.jpeg)

## El proyecto

Backend construido principalmente para ser consumido por la aplicación frontend hecha con react que puedes encontrar en
en el siguiente enlace: [react-food-delivery](https://github.com/holiweed/react-food-delivery).

## Características

- Mailing personalizado
- Confirmación de la cuenta
- Uso de graphql y servidor apollo
- Sockets web con Graphql
- Handlebears para plantillas de correo
- Postgress con TypeORM
- Cronogramas de tareas
- Linters y configuración más bonita
- Confirmación por correo electrónico
- Docker para crear la base de datos

## Instalación

Para clonar y ejecutar esta aplicación, necesitará Git y Node.js instalados en su computadora. Opcional
puedes instalar Yarn.

Desde la línea de comandos:

```bash
# Clona este repositorio
$ git clone https://github.com/DavidBarcenas/food-delivery-backend.git

# Abrir repositorio
$ cd food-delivery-backend

# Instalar dependencias
$ npm install
```

Debe tener [docker](https://www.docker.com/get-started/) instalado para crear y ejecutar el archivo
base de datos.

```bash
# Crear el la base de datos del contenedor con docker
$ docker-compose up

# Si ve el siguiente mensaje en su terminal, el contenedor se creó correctamente.
El sistema de base de datos está listo para aceptar conexiones
```

Para conectarte a la base de datos puedes usar una herramienta como [DBeaver](https://dbeaver.io/) o la que
preferir. Los datos que necesita para la conexión se pueden encontrar y configurar en el
**docker-compose.yml**.

En cualquier caso, te dejo los comandos por si quieres ver las tablas desde tu terminal.

```bash
# Primero tienes que acceder al contenedor
docker exec -it <container-name> psql -U <username> <database>

# Si accediste correctamente verás este cambio en tu terminal
food_delivery=#

# A continuación, ejecute el siguiente comando para enumerar las tablas (puede ejecutar cualquier consulta PSQL que desee)
\dt

# por ejemplo, food_delivery=# dt
# La salida del comando anterior
                 List of relations
 Schema |          Name          | Type  |
--------+------------------------+-------+
 public | category               | table |
 public | dish                   | table |
 public | email_verification     | table |
 public | order                  | table |
 public | order_item             | table |
 public | payment                | table |
 public | restaurant             | table |
 public | typeorm_metadata       | table |
 public | u
```

## Desarrollo

Inicia la aplicación en modo de desarrollo con recarga activa de código, informes de errores y mucho más.

Para que la aplicación funcione correctamente, no olvide agregar sus archivos **.env.dev, .env.prod y .env.test
files** en la raíz del proyecto (en el mismo nivel que la carpeta src).

```bash
# development
$ npm run start

# development and watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

A veces, cuando obtiene un error en la terminal, como un archivo no encontrado, se puede solucionar eliminando el archivo
**dist** desde la raíz. O bien, también puede ejecutar el comando 'npm run prebuild'_

Después de ejecutar correctamente la aplicación, puede ir a
[http://localhost:4000/graphql] (http://localhost:4000/graphql) para interactuar con el GraphQL_PlayGround
![](./.readme-static/localhost_4000_graphql.png)

## Test

```bash
# Unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# Test coverage
$ npm run test:cov
```

## Notas

No olvide establecer las variables de entorno. En el proyecto hay un archivo llamado
**.env.dev.example** allí tiene todas las variables que necesitarás.

# Licencia

Siéntase libre de bifurcar este proyecto y mejorarlo. ¡Regala un ⭐️ si te gusta este proyecto!
