# Dogs vrs Cats - Voting app

## Arquitectura

![Architecture diagram](architecture.excalidraw.png)

* front-end web app en [Python](/vote) que te permite votar entre dos opciones
* [Redis](https://hub.docker.com/_/redis/) que recolecta nuevos votos
* [.NET](/worker/) worker que consume votos y los almacena en…
* [Postgres](https://hub.docker.com/_/postgres/) que persiste los datos
* [Node.js](/result) Aplicación web que muestra los resultados de las votaciones en tiempo real.
  
## Notas

La aplicación de votación sólo acepta un voto por navegador del cliente. No registra votos adicionales si ya se ha enviado un voto de un cliente.

## Workshop parte 1

### Construir imagen result

* Autenticarse a Docker hub, importante recordar cual es el id de usuario.
* Revisar y comprender todas las instrucciones del archivo [Dockerfile](result/Dockerfile)
* Construir la imagen para la aplicación *result*.

```sh
  # Movernos a la carpeta de result
  cd result

  # Contruir la imagen con el comando: docker build
  sudo docker build -t [docker hub user]/result . 

  # listar imagenes 
  sudo docker images
```

### Construir imagen vote

* Autenticarse a Docker hub, importante recordar cual es el id de usuario.
* Revisar y comprender todas las instrucciones del archivo [Dockerfile](vote/Dockerfile)
* Construir la imagen para la aplicación *result*.

```sh
  # Movernos a la carpeta de result
  cd vote

  # Contruir la imagen con el comando: docker build
  sudo docker build -t [docker hub user]/vote . 

  # listar imagenes 
  sudo docker images
```

### Construir imagen worker

* Autenticarse a Docker hub, importante recordar cual es el id de usuario.
* Revisar y comprender todas las instrucciones del archivo [Dockerfile](worker/Dockerfile)
* Construir la imagen para la aplicación *result*.

```sh
  # Movernos a la carpeta de result
  cd worker

  # Contruir la imagen con el comando: docker build
  sudo docker build -t [docker hub user]/worker . 

  # listar imagenes 
  sudo docker images
```

## Workshop parte 2

Evaluar el contenido del archivo [docker-compose.yml](docker-compose.yml)

## Workshop parte 3

* Explorar todos los objetos de Kubernetes ubicados en la carpeta [k8s-deployments](k8s-deployments)
* Autenticarse al cluster
  
```sh
gcloud container clusters get-credentials sandbox-cluster-v1 --region us-central1 --project wwcode-terraform-admin
```

* Desplegar todos los objectos de kubernetes

```sh
# Movernos hacia la carpeta donde se encuentran los manifestos
cd k8s-deployments 

# Desplegar los objectos
kubectl apply -f .

```
