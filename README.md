# Dogs vrs Cats - Voting app

## Arquitectura

![Architecture diagram](architecture.excalidraw.png)

* front-end applicación web en [Python](/vote) que te permite votar entre dos opciones
* [Redis](https://hub.docker.com/_/redis/) que recolecta nuevos votos
* [.NET](/worker/) worker que consume votos y los almacena en…
* [Postgres](https://hub.docker.com/_/postgres/) que persiste los datos
* [Node.js](/result) Aplicación web que muestra los resultados de las votaciones en tiempo real.
  
## Notas

La aplicación de votación sólo acepta un voto por navegador del cliente. No registra votos adicionales si ya se ha enviado un voto de un cliente.

## Ejercicio

* Crear dos redes, una para frontend y otra para backend. Asignar estas redes según corresponda a cada servicio para garantizar la correcta comunicación entre todos los servicios y evitar accesos innecesarios.
* Persisitir los datos o archivos que sean necesarios para preservar el conteo de votos.