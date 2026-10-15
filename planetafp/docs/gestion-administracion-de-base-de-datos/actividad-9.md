# Actividad 9

## Rayanair

Una agencia de viajes desea informatizar toda la gestión de los viajeros que acuden a la agencia y los viajes que estos realizan. Tras ponernos en contacto con la agencia, ésta nos proporciona la siguiente información.

La agencia desea guardar la siguiente información de los viajeros: dni, nombre, dirección y teléfono.

De cada uno de los viajes que maneja la agencia interesa guardar el código de viaje, número de plazas, fecha en la que se realiza el viaje y otros datos. Un viajero puede realizar tantos viajes como desee con la agencia. Un viaje determinado sólo puede ser cubierto por un viajero.

Cada viaje realizado tiene un destino y un lugar de origen. De cada uno de ellos se quiere almacenar el código, nombre y otros datos que puedan ser de interés. Un viaje tiene un único lugar de destino y un único lugar de origen”.

### Datos relevantes

<table data-search="false"><thead><tr><th>Datos</th></tr></thead><tbody><tr><td>Una agencia de viajes desea informatizar toda la gestión de los viajeros que acuden a la agencia y los viajes que estos realizan.</td></tr><tr><td>La agencia desea guardar la siguiente información de los viajeros: dni, nombre, dirección y teléfono</td></tr><tr><td>De cada uno de los viajes que maneja la agencia interesa guardar el código de viaje, número de plazas, fecha en la que se realiza el viaje y otros datos.</td></tr><tr><td>Un viajero puede realizar tantos viajes como desee con la agencia. Un viaje determinado sólo puede ser cubierto por un viajero.</td></tr><tr><td>Cada viaje realizado tiene un destino y un lugar de origen.</td></tr><tr><td>De cada uno de ellos se quiere almacenar el código, nombre y otros datos que puedan ser de interés.</td></tr><tr><td>Un viaje tiene un único lugar de destino y un único lugar de origen”.</td></tr></tbody></table>

### Tabas encontradas

* Viajeros
* Viajes
* Viaje origen
* Viaje destino

#### Desarrollo de la actividad

La información del "viaje destino" viaja a "viaje" a través de una clave foránea y lo mismo con la tabla "viaje origen"

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### Problemas encontrados

* Las información que guarda "viaje destino" y "viaje origen" se puede poner en la tabla "viaje" simplificando las tablas.
* Otro problema encontrado es que cuando ponga el "id\_origen" y "id\_destino" dentro de viajes tendré que poner sus atributos también entonces la solución seria crear una tabla que sea de "lugares".

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

