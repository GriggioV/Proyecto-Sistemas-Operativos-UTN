## Sobre el proyecto

El proyecto consistía en crear una serie de procesos e hilos para simular el comportamiento de un sistema operativo utilizando Go, entre lo cual se incluyen instrucciones, syscalls y todo tipo de interacción del sistema con estos procesos. Para ello, corrimos cuatro módulos: kernel, memoria, cpu y filesystem, y realizamos diversas pruebas entre los mismos para verificar que el comportamiento fuera el esperado en diversos aspectos (mutex, bloques del filesystem, asignación correcta de espacios de memoria, entre otros).
---
## Conexiones

Para realizar las conexiones entre los módulos, que eran fundamentales, utilizamos la capacidad de Go para exponer y consumir API´s, asi es que cada vez que un módulo debía comunicarse con otro o viceversa, se exponían endpoints para manejar el motivo de la comunicación de manera específica con sus respectivos handlers. De esta manera, cada cosa que un módulo necesitara de otro, debía ser enviada en forma de una petición http a través de dicho endpoint. Esta dinámica nos facilitó mucho la comunicación entre módulos, que de otra manera hubiera tenido que hacerse utilizando un método diferente.
---
## Resultados y conclusión

El proyecto que van a ver a continuación pasó todas las pruebas necesarias y su lógica funciona y es correcta. Una gran parte de la consigna daba lugar a diferentes interpretaciones de lo que se debía hacer, por lo que no debe ser la única solución ni tampoco la más eficiente de todas, pero está probado su funcionamiento y su casi nulo consumo de la CPU al correrse, por lo cual son libres de probarlo en sus máquinas si es que así lo desean!
---

## Enunciado

https://docs.google.com/document/d/1HSZ14tk7IOfkOf-7ni0Wa6wnKZClEQA7zZyv-h0EZAY/edit?pli=1&tab=t.0
