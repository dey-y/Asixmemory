# Elementos de Clasificacion

Que es

* IEEE
  * Es el intituto de ingenieros electricos y electronicos. Es la mayor organizacion profesional tecnica del mundo
* ¿Qué hace el IEEE?
  * Define normas técnicas y estándares globales para la informática, las telecomunicaciones y la energía
* 802.11 WIFI
  * EEE 802.11 es el conjunto de normas técnicas que definen el funcionamiento de las redes inalámbricas de área local (WLAN)
* 802.3 Ethernet
  * **EEE 802.3** es el conjunto de normas técnicas que definen el funcionamiento de las **redes de área local (LAN) cableadas**, conocido popularmente como **Ethernet**.
* 802.15 Bluetooh
  * Es la norma que define cómo se conectan de forma inalámbrica los dispositivos que están a **muy corta distancia** (normalmente menos de 10 metros), creando lo que se conoce como una **Red de Área Personal (PAN)**.
* Tipo de redes
  * PAN (Personal Area Network): Red de área personal para conectar dispositivos cercanos a una persona (alcance de pocos metros usando Bluetooth o USB).
  * LAN (Local Area Network): Red de área local que conecta equipos en un espacio limitado como una casa, oficina o edificio. Si es sin cables, se llama WLAN.
  * CAN (Campus Area Network): Red de área de campus que conecta varias redes LAN en un área geográfica limitada, como una universidad o base militar.
  * MAN (Metropolitan Area Network): Red de área metropolitana que cubre un espacio mayor como una ciudad entera mediante fibra óptica.
  * WAN (Wide Area Network): Red de área amplia que abarca países o continentes enteros, conectando múltiples redes más pequeñas (Internet es el mayor ejemplo).
  * GAN (Global Area Network): Red de escala mundial que vincula redes a nivel global.
*   Tipos de cables de cobre -UTP -FTP -STP

    **UTP (**_**Unshielded Twisted Pair**_**):**

    * No tiene ningún blindaje.
    *   Muy flexible, económico y fácil de instalar.

        Sensible a interferencias externas.
    * Ideal para hogares y oficinas estándar.**FTP (**_**Foiled Twisted Pair**_**):**
    * Tiene una lámina de aluminio global que envuelve a todos los pares juntos.
    * Protección media contra interferencias exteriores.
    * Requiere conectores RJ45 metálicos.
    * Ideal para oficinas comerciales con ruido electromagnético moderado.

    **FTP (**_**Foiled Twisted Pair**_**):**

    * Tiene una lámina de aluminio global que envuelve a todos los pares juntos.
    * Protección media contra interferencias exteriores.
    * Requiere conectores RJ45 metálicos.
    * Ideal para oficinas comerciales con ruido electromagnético moderado.

    **STP (**_**Shielded Twisted Pair**_**):**

    * Cada par de hilos tiene su propio blindaje individual de malla o aluminio.
    * Protección máxima contra interferencias externas y entre los mismos cables.
    * Cable rígido, grueso y más costoso.
    * Requiere instalación obligatoria con toma de tierra.
    * Ideal para industrias y centros de datos.
*   Blindaje de los cables

    * El blindaje de los cables es una capa protectora metálica o conductora que rodea los conductores internos para bloquear interferencias externas y proteger el cable frente a daños físicos

    ¿Para qué sirve?

    * **Bloqueo de ruido:** Detiene las interferencias electromagnéticas (EMI) y de radiofrecuencia (RFI) causadas por motores, luces o cables cercanos.
    * **Aislamiento de señales:** Evita que la señal del cable salga y afecte a otros aparatos electrónicos.
    * **Protección física:** Resguarda el interior del cable contra golpes, aplastamientos, tirones y mordeduras de roedores

    Tipos Principales:

    * **Blindaje eléctrico (Apantallado):** Usa una lámina de aluminio o una malla trenzada de cobre. Actúa como una jaula de Faraday para mantener la pureza de los datos o el audio.&#x20;
    * **Blindaje mecánico (Armadura):** Usa alambres o cintas de acero en el exterior para dar solidez en instalaciones industriales o subterráneas.
* Caracteristicas de los cables  - Normas - EIA/TIA 568A y B
  * **Normas de Cableado: EIA/TIA 568A y 568B**
  * Características del Cable de Red (Upt/Par Trenzado)
  * Estructura: 8 hilos de cobre trenzados en 4 pares.
  * Propósito: Reducir la interferencia electromagnética y transmitir datos/voz.
  * Conector: Usa terminales RJ-45.
* Código de Colores (Pinout)
  * La única diferencia entre ambas normas es el intercambio de los **pares verde y naranja** (pines 1, 2, 3 y 6). Los pares azul y café se quedan exactamente igual.

<table data-search="false"><thead><tr><th>Pin</th><th>Norma T568A</th><th>NormaT568B</th></tr></thead><tbody><tr><td>1</td><td>Blanco / Verde</td><td>Blanco / Naranja</td></tr><tr><td>2</td><td>Verde</td><td>Naranja</td></tr><tr><td>3</td><td>Blanco / Naranja</td><td>Blanco / Verde</td></tr><tr><td>4</td><td>Azul</td><td>Azul</td></tr><tr><td>5</td><td>Blanco / Azul</td><td>Blanco / Azul</td></tr><tr><td>6</td><td>Naranja</td><td>Verde</td></tr><tr><td>7</td><td>Blanco / Café</td><td>Blanco / Café</td></tr><tr><td>8</td><td>Café</td><td>Café</td></tr></tbody></table>

* Tipos de Cables según su Armado
* **Cable Directo (Straight-through):**
  * **Configuración:** Mismo estándar en ambos extremos (**A - A** o **B - B**).
  * **Uso:** Conectar dispositivos **diferentes** (ej: PC a Switch, Router a Hub).
* **Cable Cruzado (Crossover):**
  * **Configuración:** Estándares diferentes en los extremos (**A - B**).
  * **Uso:** Conectar dispositivos **iguales** (ej: PC a PC, Switch a Switch).
  * _Nota: Hoy en día casi no se usa gracias a la tecnología **Auto-MDIX**, donde los puertos modernos se cruzan digitalmente de forma automática._
* Que son los pares de cables?
  * Los pares de cables (o pares trenzados) son el corazón de un cable de red. Consisten en dos hilos de cobre aislados que están entrelazados entre sí formando una especie de trenza o hélice.
  * ¿Por qué están trenzados (entrelazados)?\
    La razón principal es la física y la protección de los datos:
  * Evitan la interferencia (Crosstalk): Cuando la corriente eléctrica viaja por un cable, genera un pequeño campo magnético que puede "ensuciar" la señal del cable de al lado. Al trenzarlos, los campos magnéticos de ambos hilos se cancelan entre sí.
  * Protección externa: El trenzado también ayuda a que el ruido electromagnético del exterior (motores, luces fluorescentes, cables eléctricos) afecte a ambos hilos por igual, permitiendo al equipo receptor limpiar la señal fácilmente mediante una técnica llamada transmisión diferencial.
* RJ 45 - RJ 49 -RJ11 - RS232 (consola)
*   Tipos de Conectores y Puertos de Red, RJ-45 (Registered Jack 45)

    * **Descripción:** Es el conector estándar para redes de datos de área local (**LAN**).
    * **Pines:** **8 pines** y 8 contactos (8P8C).
    * **Cables compatibles:** UTP, FTP, STP (Categorías 5e, 6, 6A, etc.).
    * **Uso principal:** Conectar computadoras, switches, routers y Smart TVs a internet o a la red local.

    RJ-49 (Registered Jack 49)

    * **Descripción:** Es una **variante blindada del RJ-45**. Físicamente se ve casi igual, pero incluye una carcasa o pestaña metálica exterior.
    * **Pines:** **8 pines** (8P8C) + **Contacto de tierra**.
    * **Cables compatibles:** Específico para cables blindados (STP / FTP).
    * **Uso principal:** Conexiones de red en entornos con mucha interferencia electromagnética (fábricas, centros de datos). La pestaña metálica toca el blindaje del cable para desviar el ruido eléctrico a la toma de tierra.

    RJ-11 (Registered Jack 11)

    * **Descripción:** Es el conector estándar de la **telefonía analógica tradicional**. Es notablemente más pequeño que un RJ-45.
    * **Pines:** Físicamente tiene espacio para 6 pines, pero normalmente **solo usa 2 o 4 pines** (6P2C o 6P4C).
    * **Cables compatibles:** Cable telefónico básico de dos hilos de cobre.
    * **Uso principal:** Conectar el teléfono fijo a la roseta de la pared, o conectar la línea telefónica analógica al puerto DSL de un módem.

    RS-232 / Puerto de Consola

    * **Descripción:** Es un estándar antiguo de **comunicación serial** (en serie). Hoy en día, en redes, sobrevive casi exclusivamente como el "Puerto de Consola" para administrar equipos.
    * **Formatos físicos comunes:**
      * Conector **DB9** (forma de D, con 9 pines).
      * Adaptado a formato **RJ-45** (cable _Rollover_ o cable de consola de Cisco).
      * Moderno en formato **USB / USB-C**.
    * **Uso principal:** Conectarse directamente a la "entraña" de un switch o router empresarial para configurarlo desde una terminal (como Putty o TeraTerm) cuando el equipo no tiene internet o está recién salido de fábrica.
* ¿Que tipo de cable podria utilizar en industrias o cerca de equipamiento electrico?&#x20;
  *   El tipo de cable ideal (Por su blindaje)

      * **Cables STP (Shielded Twisted Pair):** Cada par de hilos de cobre viene envuelto en una lámina de aluminio independiente, y el conjunto lleva una malla metálica global. Son los más resistentes contra interferencias extremas.
      * **Cables S/FTP (Screened Foamed Twisted Pair):** El cable entero tiene una malla metálica exterior y, además, cada par trenzado tiene su propia lámina de aluminio. Es el estándar de oro para la industria.
      * **Cables F/UTP (Foiled Twisted Pair):** Tienen una sola lámina de aluminio global que envuelve a los 4 pares. Sirven para interferencias moderadas, pero para la industria pesada es mejor el STP o S/FTP.

      El conector correcto

      * Debes usar conectores **RJ-49 (o RJ-45 blindados con carcasa metálica)**.
      * La lámina o malla de aluminio del cable debe hacer contacto físico con la carcasa metálica del conector para poder desviar toda la interferencia (el ruido eléctrico) hacia la toma de tierra de los switches o paneles de parcheo industrial.

      La chaqueta o cubierta exterior (Seguridad e higiene)En industrias no solo importa la electricidad, sino también el entorno físico:

      * **LSZH (Low Smoke Zero Halogen):** Obligatorio en muchos países. Si hay un incendio, no propaga la llama y no emite gases tóxicos ni humo negro denso.
      * **Cubiertas PUR (Poliuretano):** Si el cable va a estar expuesto a aceites minerales, grasas mecánicas, cortes constantes o abrasión en la fábrica.
