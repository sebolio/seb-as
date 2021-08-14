# Planificador
### Administrador de TODOs desarrollado en VueJS que corre sobre Meteor

![imagen](https://user-images.githubusercontent.com/71235349/129432202-09a3420c-7a46-4078-8693-93a49a88bbc9.png)

Este programa permite registrarse como usuario, gestionar una lista de tareas pendientes y marcarlas como terminadas. Se utilizan librerías propias de Meteor y Vue para manejar los estados de los usuarios y la suscripción a cambios en la base de datos.

Para docker se utiliza una imagen no oficial pero muy popular, que se encuentra en el repositorio oficial de Docker.

El servidor de Mongo viene integrado en el lanzador de `meteor` en el caso de levantar como desarrollador, mientras que al levantar como usuario se utiliza una versión dockerizada.


### Stack
* VueJS
* MongoDB
* Meteor
* Docker

## Levantar en modo Desarrollo
⛔ Se requiere tener [meteor](https://www.meteor.com/install) (si usas Windows, necesitas instalarlo mediante [chocolatey](https://chocolatey.org))
```sh
meteor run
```
Acceder por el navegador:
> http://localhost:3000

## Levantar con Docker
⛔ En macOS se recomienda configurar Docker para usar `overlay2` en vez de `aufs`, para construir más rápido el contenedor de Meteor
> Abrir Dashboard de Docker Desktop y en ajustes de `Docker Engine`, añadir el siguiente parámetro:
> ```json
>  "storage-driver": "overlay2"
>```

Construir y levantar la aplicación:
```sh
docker-compose up
```
Cuando veas mensajes de `planificador-mongo` podrás acceder por el navegador:
> http://localhost

