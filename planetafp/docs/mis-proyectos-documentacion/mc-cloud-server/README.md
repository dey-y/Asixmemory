---
icon: server
---

# MC Cloud Server

El proposito de esta documentacion es aprender a crear un servidor en la nube para utilizar servicios que requieran estar encendidas 24/7

**Porque hago esto?**\
El proposito del porque lo hago es para que en vez de hostear una partida de minecraft en mi ordenador lo haga en un servidor, si eta hosteada en un servidor cualquiera puede acceder a la partida e cualquier momento del dia pero si lo hosteo en mi pc solo podran jugar cuando yo decida conectarme.

**Ej de serivicios:**\
Crear u asistente de inteligencia artificial y poder comunicarte con el desde cualquier lugar ya sea para crear un bot en alguna app como puede ser Discord, Whattsap, Telegram entre otras aplicaciones.

**Como obtengo un servidor en la nube?**\
Hay multiplesa empresas que ofrecen servicios en la nube como oracle o google, en mi caso yo decidi usar oracle porque ofrece 4 nucelos y 24 gb ram el primer mes de uso, una vez acabado este plan gratuito solo ofrece 1 nucleo y 12 gb ram.

**Como crear el Servior en la nube**

Una vez teniendo la cuenta creada en oracle crearemos una instancia.

<figure><img src="../../.gitbook/assets/imagen (35).png" alt=""><figcaption></figcaption></figure>

Paso 1: Información básica

**1.1 Nombre** → `Cloudserver`

* **Para qué sirve:** identifica la instancia en la consola. No afecta al funcionamiento; también se usa como nombre de host.
* **Por qué:** conviene un nombre claro para reconocerla si luego tienes varias VMs.

<figure><img src="../../.gitbook/assets/imagen (39).png" alt=""><figcaption></figcaption></figure>

**1.2 Compartimento** → `(root)`

* **Para qué sirve:** los compartimentos son carpetas lógicas para organizar y controlar permisos de recursos.
* **Por qué dejarlo en root:** para un proyecto personal con un solo servidor no hace falta crear más.

<figure><img src="../../.gitbook/assets/imagen (40).png" alt=""><figcaption></figcaption></figure>

**1.3 Colocación → Dominio de disponibilidad** → `AD 1 (EU-MADRID-3-AD-1)`

* **Para qué sirve:** es el centro de datos físico dentro de la región donde se ejecuta la VM.
* **Por qué:** Madrid solo tiene uno, así que no hay que decidir. Además, el shape Always Free depende de la capacidad disponible en el dominio; si da error de "Out of capacity", se reintenta más tarde.

<figure><img src="../../.gitbook/assets/imagen (42).png" alt=""><figcaption></figcaption></figure>

**1.4 Opciones avanzadas → Tipo de capacidad** → `Capacidad bajo demanda`

* **Para qué sirve:** define cómo se asigna el hardware a tu VM.
* **Por qué esta opción:** es la normal y estable. La _capacidad preferente_ es más barata pero Oracle puede reclamarla en cualquier momento, lo que apagaría tu servidor. Reserva de capacidad y host dedicado son de pago y innecesarias aquí.

<figure><img src="../../.gitbook/assets/imagen (41).png" alt=""><figcaption></figcaption></figure>

#### Paso 2: Imagen y forma

**2.1 Imagen (sistema operativo)** → cambiar a `Canonical Ubuntu 24.04` (versión aarch64/ARM)

* **Para qué sirve:** es el sistema operativo que se instala en la VM.
* **Por qué cambiarla:** La que viene por defecto vale para Minecraft pero Ubuntu tiene más guías disponibles.
* **Cómo:** _Cambiar imagen_ → Ubuntu → Canonical Ubuntu 24.04 → _Seleccionar imagen_.

<figure><img src="../../.gitbook/assets/imagen (43).png" alt=""><figcaption></figcaption></figure>

**2.2 Forma (hardware)** → `VM.Standard.A1.Flex` (Siempre Libre-Elegible), **2 OCPU y 12 GB**

* **Para qué sirve:** define la CPU, la RAM y el ancho de banda de la VM. Ampere A1 es ARM.
* **Por qué:** 1 OCPU / 6 GB se queda justo para Minecraft. El límite Always Free es 4 OCPU y 24 GB en total, así que 2/12 deja margen. Se cambia en _Cambiar de forma_.
* **Ojo:** la etiqueta "Siempre Libre-Elegible" debe seguir visible tras el cambio.

<figure><img src="../../.gitbook/assets/imagen (44).png" alt=""><figcaption></figcaption></figure>

#### Paso 3: Opciones avanzadas (Gestión)

**3.1 Servicio de metadatos (IMDS):** dejar **desactivado** ("Requerir encabezado de autorización").

* **Para qué sirve:** da datos de la instancia a las aplicaciones que corren dentro. Exigir IMDSv2 es más seguro, pero solo si la imagen lo soporta; no hace falta aquí.

<figure><img src="../../.gitbook/assets/imagen (45).png" alt=""><figcaption></figcaption></figure>

**3.2 Script cloud-init:** dejar **vacío**.

* **Para qué sirve:** ejecuta comandos automáticamente en el primer arranque (instalar Java, etc.). Lo haremos a mano para aprender.

<figure><img src="../../.gitbook/assets/imagen (46).png" alt=""><figcaption></figcaption></figure>

**3.3 Etiquetas:** dejar **vacío**.

* **Para qué sirve:** organizar y filtrar recursos cuando tienes muchos.

<figure><img src="../../.gitbook/assets/imagen (47).png" alt=""><figcaption></figcaption></figure>

**3.4 Configuración de disponibilidad → Migraciones en vivo**

→ `Deja que Oracle Cloud Infrastructure elija la mejor opción de migración`, con **Restaurar el estado del ciclo de vida** activado.

* **Para qué sirve:** define qué ocurre con la VM cuando Oracle hace mantenimiento del hardware donde se ejecuta.
* **Por qué esta opción:** Oracle decide por sí solo si migra la VM en vivo o la reinicia, sin intervención. Es la más simple para un servidor personal. Las otras opciones no aportan ventaja:
  * _Migración en vivo si es posible:_ no todas las formas la soportan y, si falla, reinicia igualmente.
  * _Solo notificación:_ obliga a reiniciar a mano antes de la fecha límite.
* **Restaurar el estado (activado):** tras un reinicio por mantenimiento, la VM vuelve a quedar **encendida**. Si estuviera desactivado, quedaría detenida y habría que arrancarla manualmente, lo que rompe el 24/7.
* **Nota:** para que Minecraft también vuelva solo tras un reinicio, hay que configurar un servicio `systemd` (pendiente en pasos posteriores).

<figure><img src="../../.gitbook/assets/imagen (48).png" alt=""><figcaption></figcaption></figure>



**3.5 Agente de nube Oracle:** dejar los plugins por defecto.

* **Para qué sirve:** recoge métricas y facilita la gestión de la VM desde la consola.

<figure><img src="../../.gitbook/assets/imagen (49).png" alt=""><figcaption></figcaption></figure>

#### Paso 4: Seguridad

**4.1 Instancia blindada** → dejar **desactivada**

* **Para qué sirve:** protege el firmware y el arranque de la VM contra malware de bajo nivel (arranque seguro, arranque medido y módulo TPM).
* **Por qué desactivada:** es una protección avanzada pensada para entornos con requisitos estrictos de cumplimiento. Para un servidor de Minecraft personal no aporta una ventaja práctica, y una vez activada la instancia queda más limitada (solo se puede cambiar su nombre). Tampoco se puede combinar con computación confidencial.

<figure><img src="../../.gitbook/assets/imagen (50).png" alt=""><figcaption></figcaption></figure>

**4.2 Opciones avanzadas → Atributos de seguridad (ZPR)** → dejar **vacío**

* **Para qué sirve:** permiten aplicar políticas de Zero Trust Packet Routing (ZPR), que controlan qué recursos pueden comunicarse entre sí dentro de la red de Oracle.
* **Por qué vacío:** es un control para redes empresariales con muchos recursos. Con una sola VM, la seguridad de red se gestiona con la Security List y el firewall de la VM (puerto 25565 y SSH).

<figure><img src="../../.gitbook/assets/imagen (51).png" alt=""><figcaption></figcaption></figure>

#### Paso 5: Networking (Redes)

**5.1 Nombre de VNIC** → dejar **vacío**

* **Para qué sirve:** es la tarjeta de red virtual de la VM. Si no pones nombre, Oracle genera uno automático.
* **Por qué:** con una sola VM no hace falta distinguirla.

<figure><img src="../../.gitbook/assets/imagen (52).png" alt=""><figcaption></figcaption></figure>

**5.2 Red primaria** → `Crear una nueva red virtual en la nube` → nombre `vcn-minecraft`, compartimento `(root)`

* **Para qué sirve:** la VCN es la red privada dentro de Oracle donde viven todas tus VMs.
* **Por qué:** no existía ninguna VCN, así que se crea aquí mismo.

<figure><img src="../../.gitbook/assets/imagen (53).png" alt=""><figcaption></figcaption></figure>

**5.3 Subred** → `Crear nueva subred pública` → nombre `subred-publica-minecraft`, compartimento `(root)`, CIDR `10.0.0.0/24`

* **Para qué sirve:** una subred es una porción de la VCN. Una subred **pública** permite que sus VMs tengan IP pública y sean accesibles desde Internet.
* **Por qué pública:** los jugadores y tú (por SSH) tenéis que conectaros desde fuera.
* **CIDR `/24`:** define el rango de IPs privadas (unas 250 direcciones), de sobra para una VM.

<figure><img src="../../.gitbook/assets/imagen (54).png" alt=""><figcaption></figcaption></figure>

**5.4 Asignación de IPv4 privada** → `Asignar automáticamente la dirección IPv4 privada`

* **Para qué sirve:** es la IP interna de la VM dentro de la VCN.
* **Por qué:** Oracle elige una libre; no hay motivo para fijarla a mano.

<figure><img src="../../.gitbook/assets/imagen (55).png" alt=""><figcaption></figcaption></figure>

**5.5 Asignación de IPv4 pública** → **activada**

* **Para qué sirve:** es la IP con la que entran los jugadores y con la que te conectas por SSH.\
  **Por qué:** sin ella la VM no sería accesible desde Internet.\
  **Nota:** es una IP efímera. Se mantiene al apagar y encender la VM, pero se pierde si eliminas la instancia.\
  El interruptor solo se habilita cuando la subred seleccionada es pública.

<figure><img src="../../.gitbook/assets/imagen (72).png" alt=""><figcaption></figcaption></figure>

**5.6 Asignación de IPv6** → desactivada

* **Para qué sirve:** da a la VM una dirección IPv6.
* **Por qué:** Minecraft y SSH funcionan por IPv4

**5.7 Añadir claves SSH** → `Genere un par de llaves para mí`

* **Para qué sirve:** es la forma de entrar a la VM sin contraseña. La **pública** se instala en la VM y la **privada** la guardas tú.
* **Por qué:** es lo más cómodo si no tienes un par propio.
* **Importante:** pulsa **Descargar clave privada** y **Descargar la clave pública** antes de crear la instancia. La privada no se vuelve a mostrar y sin ella no podrás entrar.

<figure><img src="../../.gitbook/assets/imagen (73).png" alt=""><figcaption></figcaption></figure>

**5.7.1 Descargar las dos claves** → _Descargar clave privada_ y _Descargar la clave pública_

* **Resultado:** dos archivos en `Downloads`:
  * `ssh-key-2026-10-02.key` → clave **privada**
  * `ssh-key-2026-10-02.key.pub` → clave **pública**
* **Por qué ahora:** la privada solo se muestra en este momento. Si se crea la instancia sin descargarla, no se podrá entrar por SSH.

**5.7.2 Moverlas a la carpeta `.ssh`** (PowerShell, en `C:\Users\TU_USUARIO\Downloads`)

```
mkdir $env:USERPROFILE\.ssh
Move-Item .\ssh-key-2026-10-02.key $env:USERPROFILE\.ssh\
Move-Item .\ssh-key-2026-10-02.key.pub $env:USERPROFILE\.ssh\
```

* **Ubicación final:** `C:\Users\TU_USUARIO\.ssh\`
* **Para qué sirve:** `.ssh` es la carpeta donde el cliente SSH busca las claves por convención, y mantiene la privada fuera de `Downloads`.
* Si `mkdir` indica que la carpeta ya existe, no pasa nada.

**5.7.3 Restringir los permisos de la clave privada**

```
icacls $env:USERPROFILE\.ssh\ssh-key-2026-10-02.key /inheritance:r /grant:r "$($env:USERNAME):R"
```

* **Para qué sirve:** deja el archivo accesible solo para tu usuario, en modo lectura.
* **Por qué:** SSH rechaza claves privadas con permisos abiertos. Debe responder `Successfully processed 1 files`.

**5.7.4 Comprobar que están en su sitio**

```
dir $env:USERPROFILE\.ssh
```

* Deben aparecer los dos archivos.

#### Paso 6: Almacenamiento

**6.1 Tamaño de volumen de arranque personalizado** → desactivado (46,6 GB por defecto)

* **Para qué sirve:** el volumen de arranque es el disco donde se instala Ubuntu y donde vivirá el servidor de Minecraft.
* **Por qué:** 46,6 GB sobran para el sistema, Java, Paper y varios mundos. El límite Always Free son 200 GB de almacenamiento en total, así que podrías ampliarlo si el mundo crece mucho.

<figure><img src="../../.gitbook/assets/imagen (74).png" alt=""><figcaption></figcaption></figure>

**6.2 Utilizar cifrado en tránsito** → activado

* **Para qué sirve:** cifra los datos que viajan entre la instancia y su disco.
* **Por qué:** viene activado por defecto, no tiene coste y añade seguridad.

<figure><img src="../../.gitbook/assets/imagen (75).png" alt=""><figcaption></figcaption></figure>

**6.3 Cifrar este volumen con una clave que administras** → desactivado

* **Para qué sirve:** permite usar tu propia clave de cifrado desde una bóveda (Vault) en lugar de la que gestiona Oracle.
* **Por qué:** es una opción para entornos con requisitos de control estrictos. Por defecto Oracle ya cifra el volumen con sus claves.

<figure><img src="../../.gitbook/assets/imagen (76).png" alt=""><figcaption></figcaption></figure>

**6.4 Volúmenes de bloque** → vacío (no adjuntar ninguno)

* **Para qué sirve:** son discos adicionales que se conectan a la VM.
* **Por qué:** con un solo disco es suficiente. El botón _Adjuntar volumen de bloque_ aparece deshabilitado porque la instancia aún no existe.

<figure><img src="../../.gitbook/assets/imagen (77).png" alt=""><figcaption></figcaption></figure>

**6.5 Siguiente** → pulsa **Siguiente** para ir a la pantalla de **Revisión**.

