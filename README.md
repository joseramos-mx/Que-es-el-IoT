# Que-es-el-IoT-y-como-aplicarlo-al-area-medica
Tu primer deploy con Azure IoT Hub y raspberry pi además de Azure IoT Central para monitorización continua de pacientes.

Este tutorial es originalmente de: [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-node-get-started)

En este tutorial, empezará por aprender los principios básicos del uso de Raspberry Pi que ejecuta Raspbian. A continuación, aprenderá a conectar sin problemas los dispositivos en la nube con [Azure IoT Hub](https://docs.microsoft.com/es-mx/azure/iot-hub/about-iot-hub). Para obtener ejemplos de Windows 10 IoT Core, vaya al [Centro de desarrollo de Windows](https://www.windowsondevices.com/).

¿Aún no tiene un kit? Pruebe el [simulador en línea de Rapsberry Pi](https://docs.microsoft.com/es-mx/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started). También puede comprar un nuevo kit [aquí](https://azure.microsoft.com/develop/iot/starter-kits).

# Ejecutar una aplicación de ejemplo en Pi

### Clonar una aplicación de ejemplo e instalar los paquetes de requisitos previos

* 1. Conéctese a Raspberry Pi con uno de los siguientes clientes SSH del equipo host:

###### Usuarios de Windows

a. Descargue e instale [PuTTY](https://www.putty.org/) para Windows.

b. Copie la dirección IP de Pi en la sección de nombre de host (o dirección IP) y seleccione SSH como el tipo de conexión.

![Putty](https://docs.microsoft.com/es-mx/azure/iot-hub/media/iot-hub-raspberry-pi-kit-node-get-started/7-putty-windows.png)

> El nombre de usuario predeterminado es pi y la contraseña es raspberry.

###### Usuarios de Mac y Ubuntu

Use el cliente de SSH integrado en Ubuntu o macOS. Quizás deba ejecutar ssh pi@<ip address of pi> para conectar Pi mediante SSH.

  * 2. Instale Node.js y NPM en Pi.
  
  En primer lugar, compruebe la versión de Node.js.

```
  node -v
```
Si la versión es anterior a la 10.x, o bien si no hay ninguna versión de Node.js en Pi, instale la versión más reciente.
 
 ```
 curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash sudo apt-get -y install nodejs
 ```

 * 3. Clone la aplicación de ejemplo.
 
 ```
 git clone https://github.com/Azure-Samples/azure-iot-samples-node.git
  ```
 
 * 4. Instale todos los paquetes para el ejemplo. La instalación incluye el SDK de dispositivo IoT de Azure, la biblioteca del sensor BME280 y la biblioteca de cableado de Pi.
 
```
 cd azure-iot-samples-node/iot-hub/Tutorials/RaspberryPiApp npm install
```
 
> Este proceso de instalación puede llevar varios minutos en función de la conexión de red.

# Configurar la aplicación de ejemplo

* 1. Abra el archivo config mediante la ejecución de los comandos siguientes:
 
 ```
 nano config.json
 ```
 
Hay dos elementos en este archivo que se pueden configurar. El primero es interval, que define el intervalo de tiempo (en milisegundos) entre los mensajes que se envían a la nube. El segundo es simulatedData, un valor booleano que indica si se usan los datos de sensor simulados o no.

Si no tiene el sensor, establezca el valor simulatedData en true para que la aplicación de ejemplo cree y use datos de sensor simulados.

Nota: La dirección de I2C usada en este tutorial es 0x77 de forma predeterminada. En función de su configuración, también podría ser 0x76: si encuentra un error de I2C, intente cambiar el valor a 118 y compruebe si se resuelve. Para ver qué dirección usa el sensor, ejecute sudo i2cdetect -y 1 en un shell de Raspberry Pi.
 
 ```json
 

{
    "simulatedData":  true,
    "interval": 200,
    "deviceId": "Raspberry Pi Node",
    "LEDpinGPIO": 24,
    "messageMax": 256,
    "credentialPath": "~/.iot-hub",
    "temperatureAlert": 30,
    "transport": "mqtt",
    "iotEdgeRootCertFilePath": null,
    "i2cOption":{
           "pin": 9,
           "i2cBusNo": 1,
           "i2cAddress": 119
    }
   }
  ```
 * 2. Guarde y salga al presionar Control-O > Entrar > Control-X.

# Ejecutar la aplicación de ejemplo
 
Ejecute la aplicación de ejemplo mediante el comando siguiente:
```
 sudo node index.js '<YOUR AZURE IOT HUB DEVICE CONNECTION STRING>'
 ```
 
 # Tutorial: Implementación y tutorial de una plantilla de aplicación de supervisión continua de pacientes
 
 https://docs.microsoft.com/es-mx/azure/iot-central/healthcare/tutorial-continuous-patient-monitoring
