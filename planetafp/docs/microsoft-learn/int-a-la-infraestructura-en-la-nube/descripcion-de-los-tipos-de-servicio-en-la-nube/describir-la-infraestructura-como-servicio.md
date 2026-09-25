# Describir la infraestructura como servicio

La infraestructura como servicio (IaaS) es la categoría más flexible de servicios en la nube. Proporciona la cantidad máxima de control para los recursos en la nube. En un modelo iaaS, el proveedor de nube es responsable de mantener el hardware, la conectividad de red a Internet y la seguridad física. \
Usted es responsable de todo lo demás, incluyendo:

* Instalación, configuración y mantenimiento del sistema operativo
* Configuración de red
* Configuración de base de datos y almacenamiento

Con IaaS, básicamente está alquilando el hardware en un centro de datos en la nube, pero lo que hace con ese hardware le corresponde.

Anteriormente, aprendió cómo el modelo de responsabilidad compartida divide las tareas entre usted y el proveedor de nube. En el diagrama siguiente se muestran las capas de infraestructura individuales, como redes, almacenamiento, servidores y tiempo de ejecución. Resalta las capas en las que operas en cada modelo de servicio.

<figure><img src="../../../.gitbook/assets/imagen (11).png" alt=""><figcaption></figcaption></figure>

### Enfoque de responsabilidad en IaaS <a href="#responsibility-focus-in-iaas" id="responsibility-focus-in-iaas"></a>

En IaaS, el proveedor de nube es responsable de la infraestructura física y la conectividad a Internet. La mayor parte de la pila de la carga de trabajo se administra, como los sistemas operativos, la aplicación de revisiones, la configuración y muchos controles de seguridad. Este modelo ofrece máxima flexibilidad y la mayor responsabilidad operativa.

<figure><img src="../../../.gitbook/assets/imagen (12).png" alt=""><figcaption></figcaption></figure>

### Escenarios <a href="#scenarios" id="scenarios"></a>

Entre los escenarios comunes en los que IaaS puede tener sentido se incluyen:

* **Migración mediante lift-and-shift**: configure los recursos de la nube similares al centro de datos de sus instalaciones y, a continuación, mueva las cargas de trabajo a la infraestructura de IaaS.
* **Pruebas y desarrollo**: debe replicar rápidamente las configuraciones establecidas para entornos de desarrollo y pruebas. Puede iniciar o apagar diferentes entornos rápidamente con una estructura iaaS mientras mantiene un control completo.
