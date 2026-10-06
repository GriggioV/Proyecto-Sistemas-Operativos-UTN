# Simulador de Sistema Operativo en Go

<p align="center">
  <b>Proyecto académico de arquitectura de sistemas operativos simulando procesos, hilos, memoria, CPU y un sistema de archivos mediante una arquitectura modular en Go.</b>
</p>

---

## 📋 Descripción del Proyecto

Este proyecto consiste en el desarrollo de un simulador de sistema operativo implementado en **Go**. El objetivo principal fue modelar el comportamiento interno de un SO mediante la gestión de procesos e hilos, la ejecución de instrucciones, el manejo de llamadas al sistema (*syscalls*) y la interacción concurrente de los componentes del sistema.

Para lograr una arquitectura limpia y desacoplada, el sistema se dividió en cuatro módulos independientes que se comunican entre sí:
* **Kernel:** Orquestador central de la planificación, estados de procesos e hilos, y atención de syscalls.
* **Memoria:** Encargado de la asignación y gestión de espacios de memoria para los procesos.
* **CPU:** Módulo responsable de la ejecución de las instrucciones recibidas y el ciclo de instrucción.
* **Filesystem:** Sistema de archivos simulado que administra bloques y operaciones de lectura/escritura.

Se realizaron diversas pruebas exhaustivas para verificar el correcto funcionamiento en escenarios complejos, tales como la administración de exclusión mutua (*mutex*), la gestión de bloques en el sistema de archivos y la asignación precisa de memoria.

---

## 🔌 Arquitectura de Conexiones

La comunicación entre los diferentes módulos es un pilar fundamental del diseño. Para resolverla de manera robusta y escalable, se aprovechó la capacidad nativa de Go para exponer y consumir APIs. 

* **Modelo Cliente-Servidor HTTP:** Cada módulo expone endpoints específicos con sus respectivos *handlers* para atender requerimientos particulares de otros componentes.
* **Desacoplamiento:** Cualquier interacción, solicitud de datos o notificación entre el Kernel, la CPU, la Memoria y el Filesystem se realiza mediante peticiones HTTP estandarizadas.
* **Ventajas:** Este enfoque simplificó drásticamente la sincronización y el pasaje de mensajes entre módulos distribuidos localmente, facilitando el mantenimiento y la extensibilidad del código.

---

## 📊 Resultados y Conclusión

El simulador ha superado satisfactoriamente todas las pruebas funcionales estipuladas por la cátedra, demostrando que la lógica implementada es correcta y estable. 

Dado que una parte importante de la consigna permitía diferentes interpretaciones de diseño, esta solución representa una de las aproximaciones posibles al problema. Si bien puede no ser la única ni la más optimizada en todos los escenarios, se destaca por:
* **Robustez:** Comportamiento verificado en múltiples escenarios de concurrencia.
* **Eficiencia:** Un consumo de CPU prácticamente nulo durante su ejecución en reposo o baja carga.

¡Los invitamos a clonar el repositorio, probarlo en sus máquinas y explorar su funcionamiento!

---

## 🔗 Enlaces de Interés

* [Enunciado Oficial del Proyecto](https://docs.google.com/document/d/1HSZ14tk7IOfkOf-7ni0Wa6wnKZClEQA7zZyv-h0EZAY/edit?pli=1&tab=t.0)