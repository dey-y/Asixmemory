# Crear VCN

**Dónde ir**

1. Menú ☰ (arriba a la izquierda) → **Networking** → **Redes virtuales en la nube**.

<figure><img src="../../.gitbook/assets/imagen (56).png" alt=""><figcaption></figcaption></figure>

Pulsa **Crear VCN**.

**Paso A: Crear la VCN**

**Nombre** → `vcn-minecraft`

* **Para qué sirve:** identifica tu red privada en Oracle.

**Compartimento** → `(root)`

**Bloque CIDR IPv4** → `10.0.0.0/16`

* **Para qué sirve:** define el rango total de IPs privadas de la VCN (unas 65.000). Dentro de él se crean las subredes.
* **Por qué:** es el valor estándar y sobra espacio para este proyecto.

**Resto de opciones** → por defecto. Deja marcado el uso de nombres de host DNS en la VCN y pulsa **Crear VCN**.

<figure><img src="../../.gitbook/assets/imagen (57).png" alt=""><figcaption></figcaption></figure>

**Paso B: Crear los componentes de red (solo con el formulario manual)**

Este formulario crea **solo la VCN**, sin subred ni salida a Internet. Esto lo tengo que corregir: te mencioné el asistente, que lo crea todo automáticamente (**Iniciar asistente de VCN** → _Crear VCN con conectividad a Internet_). Con el formulario manual hay que hacerlo a mano dentro de la VCN:

**B.1 Puerta de enlace de Internet**

* **Dónde:** VCN → **Puertas de enlace de Internet** → **Crear puerta de enlace de Internet**.
* **Para qué sirve:** es la salida y entrada a Internet de la VCN. Sin ella la VM no sería accesible desde fuera.

<figure><img src="../../.gitbook/assets/imagen (58).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (59).png" alt=""><figcaption></figcaption></figure>

Nombre: `igw-minecraft`, compartimento `(root)`.

Pulsa **Crear puerta de enlace de Internet** y espera a que quede en estado _Disponible_.

<figure><img src="../../.gitbook/assets/imagen (60).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (61).png" alt=""><figcaption></figcaption></figure>

**Siguiente (B.2):** pestaña **Enrutamiento** →

<figure><img src="../../.gitbook/assets/imagen (62).png" alt=""><figcaption></figcaption></figure>

Tabla de rutas por defecto → _Añadir reglas de ruta_:

<figure><img src="../../.gitbook/assets/imagen (63).png" alt=""><figcaption></figcaption></figure>

* Tipo de destino: _Puerta de enlace de Internet_
* Bloque CIDR de destino: `0.0.0.0/0`
* Puerta de enlace: `igw-minecraft`

<figure><img src="../../.gitbook/assets/imagen (64).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/imagen (65).png" alt=""><figcaption></figcaption></figure>

####

#### Paso B.3: Crear la subred pública

* Vuelve a la VCN `vcn-minecraft` y entra en la pestaña **Subredes** → **Crear subred**.

<figure><img src="../../.gitbook/assets/imagen (66).png" alt=""><figcaption></figcaption></figure>

* Rellena:
  * **Nombre:** `subred-publica-minecraft`
  * **Compartimento:** `(root)`
  * **Bloque CIDR IPv4:** `10.0.0.0/24`
  * **Tabla de rutas:** la que acabas de editar (la _Default Route Table_, que ya tiene la regla)
  * **Acceso a la subred:** **Subred pública**

<figure><img src="../../.gitbook/assets/imagen (69).png" alt=""><figcaption></figcaption></figure>

* **Security List:** la _Default Security List_
* Deja el resto por defecto y pulsa **Crear subred**.

<figure><img src="../../.gitbook/assets/imagen (70).png" alt=""><figcaption></figcaption></figure>

**Para qué sirve:** es la porción de la VCN donde vivirá la VM con IP pública. Al ser pública y usar la tabla con la ruta a Internet, la VM podrá ser accesible desde fuera.

<figure><img src="../../.gitbook/assets/imagen (71).png" alt=""><figcaption></figcaption></figure>
