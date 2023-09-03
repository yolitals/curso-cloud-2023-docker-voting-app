# Dogs vrs Cat - Voting app

## Arquitectura

![Architecture diagram](architecture.excalidraw.png)

* front-end applicación web en [Python](/vote) que te permite votar entre dos opciones
* [Redis](https://hub.docker.com/_/redis/) que recolecta nuevos votos
* [.NET](/worker/) worker que consume votos y los almacena en…
* [Postgres](https://hub.docker.com/_/postgres/) que persiste los datos
* [Node.js](/result) Aplicación web que muestra los resultados de las votaciones en tiempo real.
  
## Notes

The voting application only accepts one vote per client browser. It does not register additional votes if a vote has already been submitted from a client.

This isn't an example of a properly architected perfectly designed distributed app... it's just a simple
example of the various types of pieces and languages you might see (queues, persistent data, etc), and how to
deal with them in Docker at a basic level.
