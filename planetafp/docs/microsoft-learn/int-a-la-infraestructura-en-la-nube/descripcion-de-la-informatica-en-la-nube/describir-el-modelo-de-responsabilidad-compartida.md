# Describir el modelo de responsabilidad compartida

Es posible que haya oído hablar del modelo de responsabilidad compartida, pero es posible que no comprenda lo que significa o cómo afecta a la informática en la nube.

### Cómo cambian las responsabilidades en la nube <a href="#how-responsibilities-shift-in-cloud" id="how-responsibilities-shift-in-cloud"></a>

Comience con un centro de datos local tradicional. Su equipo es responsable de mantener el espacio físico, garantizar la seguridad y mantener o reemplazar los servidores si ocurre algo. El departamento de TI es responsable de mantener toda la infraestructura y el software necesarios para mantener el centro de datos en funcionamiento. También es probable que sean responsables de mantener todos los sistemas actualizados y en la versión correcta.

Con el modelo de responsabilidad compartida, estas responsabilidades se comparten entre el proveedor de nube y el consumidor. La seguridad física, la alimentación, la refrigeración y la conectividad de red son responsabilidad del proveedor de nube. El consumidor no está colocado con el centro de datos, por lo que no tendría sentido que el consumidor tenga ninguna de esas responsabilidades.

Al mismo tiempo, el consumidor es responsable de los datos e información almacenados en la nube. (No querrá que el proveedor de nube pueda leer su información). El consumidor también es responsable de la seguridad de acceso, lo que significa que solo concede acceso a aquellos que lo necesitan.

Entonces, para algunas cosas, la responsabilidad depende de la situación. Si usa una base de datos SQL en la nube, el proveedor de nube sería responsable de mantener la base de datos real. Sin embargo, sigue siendo responsable de los datos que se ingieren en la base de datos. Si implementó una máquina virtual e instaló una base de datos SQL en ella, será responsable de las revisiones y actualizaciones de la base de datos, así como de mantener los datos y la información almacenados en la base de datos.

Con un centro de datos en las instalaciones, usted es responsable de todo. Con la informática en la nube, esas responsabilidades cambian. El modelo de responsabilidad compartida está muy vinculado a los tipos de servicio en la nube (que se tratan más adelante en esta ruta de aprendizaje): infraestructura como servicio (IaaS), plataforma como servicio (PaaS) y software como servicio (SaaS). IaaS sitúa la mayor responsabilidad en el consumidor y el proveedor de servicios en la nube es el responsable de los conceptos básicos de seguridad física, energía y conectividad. En el otro extremo del espectro, SaaS coloca la mayor parte de la responsabilidad con el proveedor de nube. PaaS, siendo un punto intermedio entre IaaS y SaaS, descansa en algún lugar del medio e uniformemente distribuye la responsabilidad entre el proveedor de nube y el consumidor.

### Responsabilidad por modelo de servicio <a href="#responsibility-by-service-model" id="responsibility-by-service-model"></a>

En el diagrama siguiente se resalta cómo el modelo de responsabilidad compartida informa a quién es responsable de qué, dependiendo del tipo de servicio en la nube.

<figure><img src="../../../.gitbook/assets/imagen (4) (1).png" alt=""><figcaption></figcaption></figure>

### Lo que siempre permanece contigo <a href="#what-always-stays-with-you" id="what-always-stays-with-you"></a>

Al usar un proveedor de nube, siempre será responsable de:

* La información y los datos almacenados en la nube
* Dispositivos que pueden conectarse a la nube (teléfonos móviles, equipos, etc.)
* Las cuentas e identidades de las personas, los servicios y los dispositivos dentro de su entorno

### Lo que siempre posee el proveedor <a href="#what-the-provider-always-owns" id="what-the-provider-always-owns"></a>

El proveedor de nube siempre es responsable de:

* El centro de datos físico
* La red física
* Hosts físicos
* Infraestructura

### Lo que depende del tipo de servicio <a href="#what-depends-on-the-service-type" id="what-depends-on-the-service-type"></a>

El modelo de servicio determinará la responsabilidad de cosas como:

* Sistemas operativos
* Controles de red
* APLICACIONES
* Identidad y acceso

Por ejemplo, la identidad y el acceso se comparten en PaaS y SaaS: administra sus propios usuarios, roles y directivas, mientras que el proveedor ejecuta la plataforma de autenticación (como Microsoft Entra ID). Por otro lado, la infraestructura se transfiere por completo al proveedor en cuanto se pasa de un entorno local a IaaS.
