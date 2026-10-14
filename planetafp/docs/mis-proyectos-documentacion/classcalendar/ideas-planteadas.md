---
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# Ideas planteadas

### Ideas planteadas <a href="#ideas-planteadas" id="ideas-planteadas"></a>

Estas son todas las ideas que se barajaron, en el orden en que fueron apareciendo, incluidas las que luego se descartaron.

**Plataforma**

* WhatsApp: un solo chat donde todos hablan y donde el bot anuncia.
* Discord: más opciones y mejor organización por canales.
* Pizarra física en el aula, propuesta por el delegado.

**Organización de la información**

* Un calendario con las tareas de la semana que publique el bot.
* Canales agrupados por materia. Ejemplo: Redes, con "Configuración de dispositivos en Cisco" y "Configuración de redes" dentro.
* Publicar la tarea automáticamente al crearla, frente a publicarla tras una revisión. Dey se inclinó por la revisión: si hay un error, se propaga y causa confusión.
* Que los profesores gestionen las tareas hablando con el bot. Dey lo considera poco probable.

**Seguimiento personal**

* Un chat de cada persona con el bot para llevar al día lo hecho y lo pendiente. Es la idea estrella de Dey y requiere una base de datos.
* Comando de pendientes: que informe de las tareas por hacer.
* Comando de completadas: una lista con casillas para marcar lo hecho y un botón de aceptar para guardar.
* Comando de semana, con dudas sobre si mostrar los próximos 7 días o la semana en curso. Terminó convirtiéndose en el comando de agenda.

**Herramientas**

* Hermes Agent, para hacer las publicaciones y responder a los usuarios.
* n8n, como intermediario entre Notion y Hermes Agent. Dey dudaba de que hiciera falta.
* Notion, para subir las tareas nuevas.
* La API gratuita de Gemini para el chat. También se pensó en las APIs de NVIDIA, que caducan con el tiempo.
* SQLite para el estado de cada persona, frente a Notion como única base de datos.

**Alojamiento**

* El servidor que la profesora Alina usa en el centro para prácticas.
* Alternativas de reserva: un VPS barato o una Raspberry Pi.
