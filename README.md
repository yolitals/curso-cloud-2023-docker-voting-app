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

## Ejercicio

### Parte 1

* Basado en el diagrama de arquitectura, crear un docker compose para orquestar la aplicación con todos los servicios mencionados, tomar en cuenta las siguientes consideraciones:
  
  * Para redis utilizar una imagen publica (redis:alpine)
  * Para mysql utilizar una imagen publica (postgres:15-alpine)
  * La aplicación de python dentro del contenedor se ejecuta en el puerto 80.
  * La aplicación de node dentro del contenedor se ejecuta en el purto 80.
  * La aplicación para votar y la que muestra los resultados deben exponerse.

### Parte 2

* Crear dos redes, una para frontend y otra para backend. Asignar estas redes según corresponda a cada servicio para garantizar la correcta comunicación entre todos los servicios y evitar accesos innecesarios.
* Persisitir los datos o archivos que sean necesarios para preservar el conteo de votos.
