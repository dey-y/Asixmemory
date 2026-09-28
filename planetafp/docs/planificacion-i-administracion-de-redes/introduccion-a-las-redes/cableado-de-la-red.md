# Cableado de la red

## Objetivo

Lee detenidamente:

* Los dos primeros apartados se hacen en pareja.
* El apartado “Casa” lo realiza cada miembro del grupo de manera individual, pero se incorpora al documento común.  &#x20;

### Aula – cableado UTP \[2p]

1. Analiza el cableado del aula:&#x20;
2. ¿Qué tipo de cable de red se está utilizando?
3. ¿Qué características tiene el cable?
4. ¿Qué tipo de cable le acompaña?
5. Investiga las normativas para cableado de comunicación y de alimentación:\
   ¿Cumple con las normativas? Argumenta.
6. Investigar en qué casos se recomienda la instalación de cableado UTP, FTP o STP
7. En qué casos utilizamos cable cruzado y en cuáles directo. ¿Actualmente podemos utilizar indistintamente un tipo de cable u otro? Argumenta.
8. Especifica la velocidad máxima de transmisión que soportan los diferentes tipos de cables de par trenzado.&#x20;
9. Especifica el uso de cada uno de los 8 pines que componen el cable trenzado. ¿Cuántos se utilizan para transmisión?
10. Realiza una comparativa entre las normas TIA 568A / B y C

### Fibra óptica \[2p]

#### ¿Cuáles son las ventajas y desventajas de la fibra óptica?

| Ventajas                                     | Desventajas                                                    |
| -------------------------------------------- | -------------------------------------------------------------- |
| Mayor velocidad y ancho de banda             | Los hilos de vidrio del interior pueden romperse con facilidad |
| Inmunidad a interferencias                   | Coste de instalación elevado                                   |
| Los datos son muy difíciles de interceptar   | Disponibilidad limitada                                        |
| Los cables son más finos y pesan mucho menos | Empalmes complejos                                             |

#### ¿Cómo se realiza la transmisión de datos en la fibra óptica? ¿cuáles son los principios físicos que lo permiten? Argumenta (reflexión de la luz...)

La fibra óptica transmite datos mediante pulsos de luz. Un emisor, como un LED o láser, transforma la señal eléctrica en luz; esos pulsos representan los bits 0 y 1. Al llegar al destino, un receptor óptico convierte de nuevo la luz en señal eléctrica.

**Los principios físicos que lo permiten son:**

* **Reflexión interna total:** la luz rebota dentro del núcleo de la fibra sin salir al exterior. Esto ocurre porque el núcleo tiene un índice de refracción mayor que el revestimiento.
* **Refracción:** la luz cambia de dirección al pasar entre el núcleo y el revestimiento; esta diferencia permite que se produzca la reflexión interna total.
* **Atenuación y dispersión:** son fenómenos que pueden debilitar o deformar la señal con la distancia, por lo que se controlan para evitar errores.

Gracias a estos principios, la fibra puede transmitir datos a gran velocidad, a largas distancias y sin interferencias electromagnéticas.redestelecom+1

#### ¿Cuáles son las principales ventajas de la fibra óptica en relación con los cables de cobre? Argumenta.

| Ventajas                                                                                                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Mayor velocidad y ancho de banda:** la fibra puede transportar más información y soportar velocidades muy altas. En redes actuales permite alcanzar grandes capacidades de transmisión.                                                                 |
| **Mayor distancia:** la señal óptica pierde menos fuerza con el recorrido que la señal eléctrica en cobre. Por ejemplo, una LAN óptica puede alcanzar 20 km o más sin repetidores, mientras que el cableado horizontal de cobre tiene un límite de 100 m. |
| **No sufre interferencias electromagnéticas:** motores, fluorescentes, transformadores u otros cables eléctricos pueden generar ruido en el cobre. La fibra no se ve afectada por estas interferencias porque utiliza luz.                                |
| **Más seguridad:** la fibra no emite señales eléctricas ni radiación electromagnética, por lo que es más difícil interceptar la información sin que se detecte.                                                                                           |
| **Menor tamaño y peso:** un cable de fibra puede transportar mucha información ocupando menos espacio que varios cables de cobre.                                                                                                                         |
| **Mejor para el futuro:** aunque su instalación puede costar más, ofrece más capacidad de crecimiento. Por eso se utiliza habitualmente para conectar armarios de comunicaciones, plantas de un edificio o edificios diferentes.                          |

#### ¿Qué tipos de fibra óptica existen?&#x20;

* **Fibra monomodo (SMF):** tiene un núcleo muy pequeño y la luz viaja por un único camino o modo. Se utiliza en largas distancias, por ejemplo entre edificios, ciudades o redes de operadores, porque tiene menos pérdida de señal.
* **Fibra multimodo (MMF):** tiene un núcleo más grande y permite que la luz viaje por varios caminos. Se usa en distancias más cortas, como dentro de edificios, salas de comunicaciones o centros de datos.
* En resumen: la luz viaja por el núcleo, el revestimiento evita que se escape y las capas externas protegen la fibra. La fibra óptica se usa especialmente en el backbone o cableado vertical de una red.

#### ¿Cuál es la estructura de la fibra óptica?

* La estructura básica de una fibra óptica está formada por capas concéntricas que protegen la señal y el propio cable:

| Capas                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Núcleo:** parte central por la que viajan los pulsos de luz con los datos.                                                                                          |
| **Revestimiento:** capa que rodea el núcleo. Tiene un índice de refracción menor, lo que hace posible la reflexión interna total y mantiene la luz dentro del núcleo. |
| **Recubrimiento primario:** capa de plástico que protege la fibra frente a humedad, golpes y pequeñas curvaturas.                                                     |
| **Elementos de refuerzo:** fibras como kevlar o aramida que evitan que el cable se rompa al tirar de él.                                                              |
| **Cubierta exterior:** protección final del cable frente a daños físicos y condiciones ambientales.                                                                   |

#### ¿En qué casos se recomienda el uso de cada tipo?

* **Fibra monomodo:** se recomienda para enlaces de **larga distancia**, como conexiones entre edificios, campus, sedes o redes de operador. Tiene menor pérdida de señal y permite recorrer muchos kilómetros sin repetidores.
* **Fibra multimodo:** se recomienda para distancias **cortas o medias**, por ejemplo dentro de un edificio, entre armarios de comunicaciones o en un centro de datos. Suele utilizarse en redes locales porque es adecuada para el backbone interno.
* En resumen: monomodo para largas distancias y multimodo para instalaciones internas o distancias menores.

#### ¿Cuáles serían las limitaciones a la hora de implementar y mantener redes de fibra óptica?

* Las principales limitaciones al implementar y mantener fibra óptica son el coste inicial, la necesidad de personal y herramientas especializadas, y el cuidado físico que requiere el cable. Aunque ofrece gran velocidad y largas distancias, una mala instalación puede provocar pérdidas de señal o fallos.

<table data-search="false"><thead><tr><th>Limitaciones principales</th></tr></thead><tbody><tr><td><strong>Coste inicial más alto:</strong> los cables, transceptores ópticos, conectores y equipos de medición suelen costar más que los equivalentes de cobre.</td></tr><tr><td><strong>Instalación especializada:</strong> para conectar o reparar fibras se necesitan herramientas como fusionadora, cortadora de precisión y medidor de potencia u OTDR. También hace falta personal formado.</td></tr><tr><td><strong>Fragilidad y curvaturas:</strong> la fibra puede dañarse si se dobla demasiado, se estira o se aplasta. Hay que respetar el radio de curvatura y evitar tensiones durante el tendido.</td></tr><tr><td><strong>Limpieza de conectores:</strong> el polvo, grasa o arañazos en conectores y adaptadores puede causar atenuación y errores de comunicación. Por eso deben limpiarse e inspeccionarse antes de conectarlos.</td></tr><tr><td><strong>Diagnóstico más complejo:</strong> localizar una rotura, una mala fusión o una pérdida de potencia requiere instrumentos específicos; no basta con comprobar continuidad como en un cable de cobre.</td></tr><tr><td><strong>No transporta energía:</strong> la fibra solo transmite datos. A diferencia del cobre, no permite alimentar dispositivos mediante PoE, por lo que cámaras, puntos de acceso o teléfonos IP necesitan una fuente eléctrica aparte.</td></tr><tr><td><strong>Planificación necesaria:</strong> es recomendable instalar fibras de reserva porque ampliar el cableado después puede requerir obras o nuevos tendidos. En backbone se aconseja usar cables con más fibras de las necesarias para disponer de reserva ante fallos o futuras ampliaciones.</td></tr></tbody></table>

#### Conclusión <a href="#conclusin" id="conclusin"></a>

La fibra es ideal para backbone, altas velocidades y largas distancias, pero requiere una instalación más cuidadosa, materiales específicos y un mantenimiento técnico más especializado que el cobre.

### Cableado estructurado \[2p]

#### ¿Qué es el cableado troncal y cuál es la función principal en una infraestructura de red?&#x20;

El cableado troncal, también llamado cableado vertical o backbone, es la parte de la red que conecta los cuartos de telecomunicaciones, la sala principal de equipos y los diferentes pisos o zonas de un edificio.

Su función principal es transportar los datos entre las distintas partes de la infraestructura de red. Normalmente se instala con fibra óptica o cable de cobre de alta categoría, y suele organizarse con una topología en estrella, conectando los armarios de comunicaciones con una sala central.

#### ¿Cuáles son las diferencias entre cableado troncal de cobre y cableado troncal de fibra?¿En qué casos se debe elegir una u o otra?

El cableado troncal puede instalarse con cobre (UTP/STP) o con fibra óptica. La elección depende principalmente de la distancia, la velocidad necesaria, el presupuesto y si existe riesgo de interferencias eléctricas.

| Aspecto               | Troncal de cobre                                      | Troncal de fibra óptica                                         |
| --------------------- | ----------------------------------------------------- | --------------------------------------------------------------- |
| Medio de transmisión  | Señales eléctricas                                    | Pulsos de luz                                                   |
| Distancia             | Menor, está más limitado por la atenuación y el ruido | Mayor, puede alcanzar distancias muy superiores sin repetidores |
| Velocidad y capacidad | Buena con Cat 6, 6A o superiores                      | Mayor capacidad y más preparada para futuras ampliaciones       |
| Interferencias        | Puede verse afectado por ruido electromagnético       | No le afectan las interferencias electromagnéticas              |
| Coste inicial         | Más económico y fácil de instalar                     | Más caro y requiere herramientas y personal especializado       |
| Alimentación PoE      | Sí, puede transportar datos y energía                 | No, solo transmite datos                                        |

#### Revisa la webgrafía que te adjunto y explica la estructura del cableado estructurado atendiendo a:

<table><thead><tr><th width="270.683349609375"></th><th></th></tr></thead><tbody><tr><td><strong>Cableado vertical</strong></td><td>Es la columna vertebral que une la sala central de equipamiento con los armarios de telecomunicaciones de cada planta, utilizando principalmente fibra óptica y, en algunos casos, cable multipar o UTP/STP.</td></tr><tr><td><strong>Sala central de equipamiento</strong></td><td>Es el espacio principal donde se concentran los equipos de red y los paneles de parcheo del cableado vertical. Desde ella salen los enlaces hacia las distintas plantas del edificio.</td></tr><tr><td><strong>Armario de telecomunicaciones</strong></td><td>Es el punto de distribución de cada planta o zona. Recibe el cableado vertical y reparte el cableado horizontal hacia las áreas de trabajo.</td></tr><tr><td><strong>Areas de trabajo</strong></td><td>Son los espacios donde los usuarios conectan sus dispositivos a la red mediante tomas de telecomunicaciones y latiguillos.</td></tr><tr><td><strong>Entrada de servicios del edificio</strong></td><td>Es el punto por el que llegan al edificio los servicios externos, como la fibra del operador. Desde allí se conectan con la sala central de equipamiento.</td></tr></tbody></table>

### Investiga herramientas de diseño de redes \[1p]

Investiga las diferentes herramientas existentes en el mercado para diseñar una red.&#x20;

Rellena la siguiente tabla con tres opciones:

<table><thead><tr><th width="108">Herramienta</th><th width="464">Caracteristicas</th><th>Gratis/Pago</th></tr></thead><tbody><tr><td>Cisco Packet Tracer<br></td><td>Permite crear topologías mediante elementos gráficos, configurar routers y switches y simular el envío de paquetes. Está orientado principalmente al aprendizaje de redes Cisco.</td><td>Gratis</td></tr><tr><td>GNS3</td><td>Programa de código abierto para diseñar y emular redes virtuales. Permite utilizar diferentes dispositivos, acceder a sus consolas y comprobar configuraciones y protocolos.</td><td>Gratis, pero algunas imágenes de sistemas requieren licencia.<br></td></tr><tr><td><br>Diagrams.net </td><td>Herramienta para crear diagramas de red mediante símbolos, conectores, texto y plantillas. Es útil para representar visualmente la distribución de routers, switches, servidores y conexiones.<br></td><td>Gratis</td></tr></tbody></table>

### Tu casa \[2p]

Analiza e investiga la instalación de la red de tu casa.

#### ¿Qué tipo de fibra llega a tu casa: monomodo o multimodo? Argumenta

El tipo de cable que llega a mi casa es ethernet ya que utiliza un conector RJ45 por lo tanto no puedo responder  a la pregunta.

#### Especifica los tipos de cables que intervienen en la configuración

los cables que intervienen en mi router es un cable ethernet RJ45 que conecta mi pc y el otro ethernet que trae el wifi a mi casa.

#### ¿Qué tipo de router tienes? Las especificaciones del mismo.

Tengo un router ZTE ZXHN H3600P proporcionado por DIGI. Es un router WI-FI 6 de doble banda, compatible con las frecuencias de 2,4 GHz y 5GHz, y alcanza una veloidad inalambrica teorica hasta 3000mbps. Dispone de un puerto WAN Gigabit y tres puertos LAN  Gigabit RJ45 para conectar dispositivos mediante cable ethernet

### Diseña \[1p]

Selecciona una de las herramientas gratuitas anteriores y utilízala para diseñar las redes de casa y del aula. La red del aula no necesita tener los 36 equipos que tenemos. Argumenta tu decisión en el uso de esa herramienta en detrimento de las demás.

#### Escribe la IP de un dispositivo de tu casa, por ejemplo, el móvil.

Dirección ip de mi pc 192.168.1.57

#### ¿Qué topología se implementa en la red: bus, árbol, estrella...?&#x20;

Topología estrella&#x20;

#### ¿Qué características tiene ese tipo de topología?

Las caracteristicas de la topologia en estrella es que todo los dispositivos se conectan a un unico punto, en mi caso todos mis dispositivos se conectan a mi router.

Otra caracteristica es que cada equipo tiene su propia enlace al dispositivo central.

Las ventajas son que si falla un cable la red sigue funcionando, son faciles de amplia y faciles de administrar y diagnosticar.

Las desventajas son que si el dispositivo central (router) se cae se cae toda la red y el rendimiento de la red depende totalmente del dispositivo central.

#### Diseño de la red de la casa

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
