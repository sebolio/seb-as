# Planificador
### Administrador de TODOs desarrollado en VueJS que corre sobre Meteor

Este programa permite registrarse como usuario, gestionar una lista de tareas pendientes y marcarlas como terminadas. Se utilizan librerías propias de Meteor y Vue para manejar los estados de los usuarios y la suscripción a cambios en la base de datos.

Para docker se utiliza una imagen no oficial pero muy popular, que se encuentra en el repositorio oficial de Docker.

El servidor de Mongo viene integrado en el lanzador de `meteor` en el caso de levantar como desarrollador, mientras que al levantar como usuario se utiliza una versión dockerizada.

**Se puede ver funcionando en: http://planificador.seb.cl**

![screenshot](https://seb.cl/wp-content/uploads/2021/06/planificador.png)
### Stack
* VueJS
* MongoDB
* Meteor
* Docker

## Lanzar como usuario
⛔ Se requiere tener [Docker Desktop](https://www.docker.com/products/docker-desktop) (si usas Windows, al instalarlo te dará instrucciones para instalar `WSL`)

⛔ Dependiendo de tu máquina, construir Meteor puede tardar entre 1 y 5 minutos

⛔ En macOS se recomienda configurar Docker para usar `overlay2` en vez de `aufs`, para construir más rápido el contenedor de Meteor
> Abrir Dashboard de Docker Desktop y en ajustes de `Docker Engine`, añadir el siguiente parámetro:
> ```json
>  "storage-driver": "overlay2"
>```

Construir y levantar la aplicación (puede tardar hasta 5 minutos según tu máquina):
```sh
docker-compose up
```
Cuando veas mensajes de `planificador-mongo` podrás acceder por el navegador:
> http://localhost
## Lanzar como desarrollador
⛔ Se requiere tener [meteor](https://www.meteor.com/install) (si usas Windows, necesitas instalarlo mediante [chocolatey](https://chocolatey.org))
```sh
meteor run
```
Acceder por el navegador:
> http://localhost:3000
## Hacer deploy a Meteor Galaxy
Primero, crear archivo `settings.json` a partir del settings.json.example, poniendo los datos de la DB; luego, usar el siguiente comando usando el dominio generado en Galaxy.
```
DEPLOY_HOSTNAME=galaxy.meteor.com meteor deploy <APP>.meteorapp.com --settings settings.json
```
