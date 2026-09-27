# Mis primeros diagramas E-R

## Recordatorio

Antes de lanzaros a definir el diagrama, es recomendable que subrayando el texto o tomando notas os listéis lo que creéis que serán entidades, para luego añadir las que consideréis que pueden hacer falta y no se mencionan de forma directa.

Luego junto a las propuestas de entidades los atributos que os piden, destacando los que pueden ser claves candidatas para ser Clave Primaria (el identificador que toda entidad necesita) y si no hay una clara, entonces inventar una.

Una vez hecho el diagrama con las relaciones, primero calculad las Cardinalidades y según sea 1:1, 1:N o N:M, resolver dónde necesitaremos que se ubique la Clave Foránea.

## **EJERCICIO 1**

“Una empresa vende productos a varios clientes. Se necesita conocer los datos personales de los clientes (nombre, apellidos, dni, dirección y fecha de nacimiento).&#x20;

Cada producto tiene un nombre y un código, así como un precio unitario. Un cliente puede comprar varios productos a la empresa, y un mismo producto puede ser comprado por varios clientes. Los productos son suministrados por diferentes proveedores.&#x20;

Se debe tener en cuenta que un producto sólo puede ser suministrado por un proveedor, y que un proveedor puede suministrar diferentes productos. De cada proveedor se desea conocer el NIF, nombre y dirección”.

### Datos relevantes

{% columns %}
{% column %}
1 - Una empresa vende productos a varios clientes

3 - Cada producto tiene un nombre y un código, así como un precio unitario

5 - Un mismo producto puede ser comprado por varios clientes

7 - Los productos son suministrados por diferentes proveedores.&#x20;

9 - Un proveedor puede suministrar diferentes productos
{% endcolumn %}

{% column %}
2 - Se necesita conocer los datos personales de los clientes (nombre, apellidos, dni, dirección y fecha de nacimiento)

4 - Un cliente puede comprar varios productos a la empresa

6 - Un mismo producto puede ser comprado por varios clientes

8 - Un producto sólo puede ser suministrado por un proveedor
{% endcolumn %}
{% endcolumns %}

### Diagrama

<figure><img src="../.gitbook/assets/imagen (19).png" alt=""><figcaption></figcaption></figure>

* **Problemas encontrados durante el proceso:**\
  Confusiones sobre si "Empresa" deberia de ser una identidad porque al ser una empresa la que vende los productos parecia logico incluirla como entidad en el diagrama pero en el enunciado solo menciona que "la empresa vende productos a varios clientes", pero no pide en ningún momento guardar datos suyos como nombre, dirección o NIF de la empresa, etc.\
  Además, si se añadiera "Empresa" como entidad relacionada con "Producto", la relación sería de uno a muchos porque una empresa tiene muchos productos, lo que obligaría a incluir una clave foránea de empresa en cada producto. \
  Como solo existe una única empresa, ese valor sería exactamente el mismo en todas las filas de la tabla "Producto" es decir, se duplicaría innecesariamente el mismo dato en cada producto.
* **Si la relacion de empresa a provedores fuese de n:m:**\
  Si la relacion de empresa a provedores fuese de n:m requeriria de convertir Empresa en una entidad propia, con su propio identificador y atributos ya que al haber varias empresas, cada una necesita datos que las diferencien.

<figure><img src="../.gitbook/assets/imagen (23).png" alt=""><figcaption></figcaption></figure>

Asi me quedo el diagrama al principio pero luego pense, "no necesitaria una cf de productos para empresas?" porque si no, empresa que "vende" a los clientes y me di cuenta de que se trataba de una relacion ternaria, podia relacionar "Productos" con "Clientes" porque los "clientes son los que compran los productos pero las empresas los venden. Entonces el diagrama quedaria tal que asi.

<figure><img src="../.gitbook/assets/imagen (24).png" alt=""><figcaption></figcaption></figure>

Pero este diagrama no importa porque el enunciado solo menciona una empresa asi que todo a la mrd.

## **EJERCICIO 2**

“Se desea informatizar la gestión de una empresa de transportes que reparte paquetes por toda España. Los encargados de llevar los paquetes son los camioneros, de los que se quiere guardar el dni, nombre, teléfono, dirección, salario y población en la que vive.&#x20;

De los paquetes transportados interesa conocer el código de paquete, descripción, destinatario y dirección del destinatario. Un camionero distribuye muchos paquetes, y un paquete sólo puede ser distribuido por un camionero.&#x20;

De las provincias a las que llegan los paquetes interesa guardar el código de provincia y el nombre. Un paquete sólo puede llegar a una provincia. Sin embargo, a una provincia pueden llegar varios paquetes.&#x20;

De los camiones que llevan los camioneros, interesa conocer la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión puede ser conducido por varios camioneros”.

## **EJERCICIO 3**

“Se desea diseñar la base de datos de un Instituto. En la base de datos se desea guardar los datos de los profesores del Instituto (DNI, nombre, dirección y teléfono).

Los profesores imparten módulos, y cada módulo tiene un código y un nombre. Cada alumno está matriculado en uno o varios módulos. De cada alumno se desea guardar el nº de expediente, nombre, apellidos y fecha de nacimiento.

Los profesores pueden impartir varios módulos, pero un módulo sólo puede ser impartido por un profesor. Cada curso tiene un grupo de alumnos, uno de los cuales es el delegado del grupo”.

## **EJERCICIO 4**

“Se desea diseñar una base de datos para almacenar y gestionar la información empleada por una empresa dedicada a la venta de automóviles, teniendo en cuenta los siguientes aspectos:

La empresa dispone de una serie de coches para su venta. Se necesita conocer la matrícula, marca y modelo, el color y el precio de venta de cada coche. Los datos que interesa conocer de cada cliente son el NIF, nombre, dirección, ciudad y número de teléfono: además, los clientes se diferencian por un código interno de la empresa que se incrementa automáticamente cuando un cliente se da de alta en ella. Un cliente puede comprar tantos coches como desee a la empresa. Un coche determinado solo puede ser comprado por un único cliente.

El concesionario también se encarga de llevar a cabo las revisiones que se realizan a cada coche. Cada revisión tiene asociado un código que se incrementa automáticamente por cada revisión que se haga. De cada revisión se desea saber si se ha hecho cambio de filtro, si se ha hecho cambio de aceite, si se ha hecho cambio de frenos u otros. Los coches pueden pasar varias revisiones en el concesionario”.

## **EJERCICIO 5**

A partir del siguiente supuesto diseñar el modelo entidad-relación: “La clínica “SANTA PAZ” necesita llevar un control informatizado de su gestión de pacientes y médicos.

De cada paciente se desea guardar el código, nombre, apellidos, dirección, población, provincia, código postal, teléfono y fecha de nacimiento.

De cada médico se desea guardar el código, nombre, apellidos, teléfono y especialidad. Se desea llevar el control de cada uno de los ingresos que el paciente hace en el hospital. Cada ingreso que realiza el paciente queda registrado en la base de datos. De cada ingreso se guarda el código de ingreso (que se incrementará automáticamente cada vez que el paciente realice un ingreso), el número de habitación y cama en la que el paciente realiza el ingreso y la fecha de ingreso.

Un médico puede atender varios ingresos, pero el ingreso de un paciente solo puede ser atendido por un único médico. Un paciente puede realizar varios ingresos en el hospital”.
