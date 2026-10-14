# Idea final del proyecto

AgendaClase es un bot de Discord que avisa de las tareas de la clase y deja que cada alumno marque las suyas, con Notion como única base de datos.

<figure><img src="../../.gitbook/assets/imagen (31).png" alt=""><figcaption></figcaption></figure>

El delegado y Dey añaden las tareas en Notion; el bot las lee, publica los avisos en Discord y atiende los comandos de los alumnos, guardando sus marcas en Notion.

**Objetivo.** Que los 27 alumnos lleven al día lo que han hecho y lo que les falta, sin depender de una pizarra.

**Piezas**

| Pieza               | Función                                                                                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Notion              | Guarda las tareas (materia, título, fecha de entrega, descripción) y una tabla de completadas (alumno y tarea). Solo la editan el delegado y Dey. |
| Bot de Discord      | Publica los avisos programados y atiende los comandos. No usa IA. Lee Notion y guarda las tareas en memoria unos minutos para ir rápido.          |
| Servidor de Discord | Un servidor con un canal por materia.                                                                                                             |
| Servidor del centro | Aloja el bot encendido todo el día, si Alina lo permite.                                                                                          |

**Comandos**

| Comando     | Qué hace                                                                                                                                                     |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| /agenda     | Muestra esta semana y la siguiente, por días, con el estado personal de cada tarea. Las atrasadas salen primero y destacadas.                                |
| /pendientes | Muestra todo lo que falta, sin límite de fecha, ordenado por entrega y sin las completadas.                                                                  |
| /marcar     | Abre un menú de selección múltiple y un botón de confirmar para marcar lo hecho. Permite desmarcar y filtrar por materia, porque el menú admite 25 opciones. |

**Avisos automáticos**

* Por la mañana: resumen de las actividades del día.
* Por la tarde, a las 17:00: novedades publicadas en el canal de cada materia, después de que el delegado las revise.

**Reglas de uso**

* Las respuestas de los comandos son efímeras: solo las ve quien escribe, para que nadie vea las tareas hechas por otro.
* Se guardan los datos mínimos: el ID de Discord y el estado de cada tarea.
* Los avisos usan la hora de Madrid y no se envían en días sin clase.
* El acceso a los datos va en un solo módulo del código, para poder cambiar Notion por SQLite si algún día hace falta.
