# Que-es-el-IoT-y-como-aplicarlo-al-area-medica
Tu primer deploy con Azure IoT Hub y raspberry pi además de Azure IoT Central para monitorización continua de pacientes.

Este tutorial es originalmente de: [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-node-get-started)

En este tutorial, empezará por aprender los principios básicos del uso de Raspberry Pi que ejecuta Raspbian. A continuación, aprenderá a conectar sin problemas los dispositivos en la nube con [Azure IoT Hub](https://docs.microsoft.com/es-mx/azure/iot-hub/about-iot-hub). Para obtener ejemplos de Windows 10 IoT Core, vaya al [Centro de desarrollo de Windows](https://www.windowsondevices.com/).

¿Aún no tiene un kit? Pruebe el [simulador en línea de Rapsberry Pi](https://docs.microsoft.com/es-mx/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started). También puede comprar un nuevo kit [aquí](https://azure.microsoft.com/develop/iot/starter-kits).

# Ejecutar una aplicación de ejemplo en Pi

### Clonar una aplicación de ejemplo e instalar los paquetes de requisitos previos

* Conéctese a Raspberry Pi con uno de los siguientes clientes SSH del equipo host:
* 
###### Usuarios de Windows

a. Descargue e instale PuTTY para Windows.

b. Copie la dirección IP de Pi en la sección de nombre de host (o dirección IP) y seleccione SSH como el tipo de conexión.

![Putty](https://docs.microsoft.com/es-mx/azure/iot-hub/media/iot-hub-raspberry-pi-kit-node-get-started/7-putty-windows.png)
