# Que-es-el-IoT-y-como-aplicarlo-al-area-medica
Tu primer deploy con Azure IoT Hub y raspberry pi además de Azure IoT Central para monitorización continua de pacientes.

Este tutorial es originalmente de: [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-node-get-started)

En este tutorial, empezará por aprender los principios básicos del uso de Raspberry Pi que ejecuta Raspbian. A continuación, aprenderá a conectar sin problemas los dispositivos en la nube con [Azure IoT Hub](https://docs.microsoft.com/es-mx/azure/iot-hub/about-iot-hub). Para obtener ejemplos de Windows 10 IoT Core, vaya al [Centro de desarrollo de Windows](https://www.windowsondevices.com/).

¿Aún no tiene un kit? Pruebe el [simulador en línea de Rapsberry Pi](https://docs.microsoft.com/es-mx/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started). También puede comprar un nuevo kit [aquí](https://azure.microsoft.com/develop/iot/starter-kits).

# Qué debe hacer

* Crear un Centro de IoT.

* Registre un dispositivo para Pi en IoT Hub.

* Configure Raspberry Pi.

* Ejecute una aplicación de ejemplo en Pi para enviar datos de sensor a IoT Hub.

# Conocimientos que adquirirá

* Cómo crear Azure IoT Hub y obtener la cadena de conexión del nuevo dispositivo.

* Cómo conectar Pi con un sensor BME280.

* Cómo recopilar datos del sensor al ejecutar una aplicación de ejemplo en Pi.

* Cómo enviar los datos del sensor a IoT Hub.

# Crear un centro de IoT

1. Inicie sesión en Azure Portal.

2. En la página de inicio de Azure, seleccione + Crear un recurso y, después, escriba IoT Hub en el campo Buscar en Marketplace.

3. Seleccione IoT Hub en los resultados de la búsqueda y, después, haga clic en Crear.

4. En la pestaña Datos básicos, complete los campos como se indica a continuación:

* Suscripción: seleccione la suscripción que quiera usar para el centro.

* Grupo de recursos: seleccione un grupo de recursos o cree uno. Para crear uno, haga clic en Crear y escriba el nombre que quiera usar. Para usar un grupo de recursos existente, selecciónelo. Para más información, consulte Administración de grupos de recursos de Azure Resource Manager.

* Región: seleccione la región a la que quiera asignar el centro. Seleccione la ubicación más cercana a la suya. Algunas características, como los flujos de dispositivo de IoT Hub, solo están disponibles en regiones específicas. Para ver estas características limitadas, debe seleccionar una de las regiones admitidas.

* Nombre de la instancia de IoT Hub: escriba el nombre del centro. Este nombre debe ser único globalmente.

5. Seleccione Siguiente: Redes para continuar con la creación del centro.

Elija los puntos de conexión que se pueden conectar a su instancia de IoT Hub. Puede seleccionar la configuración predeterminada Punto de conexión público (todas las redes) o elegir Punto de conexión público (intervalos de IP seleccionados) o Punto de conexión privado. Acepte la configuración predeterminada para este ejemplo.

6. Seleccione Siguiente: Administración para continuar con la creación del centro.

Puede aceptar la configuración predeterminada aquí. Si lo desea, puede modificar cualquiera de los siguientes campos:

* Plan de tarifa y escala: nivel seleccionado. Puede elegir entre varios niveles, en función del número de características que desee, y del número de mensajes que envíe al día a través de su solución. El nivel gratis está pensado para la prueba y evaluación. Permite la conexión de 500 dispositivos con el centro de IoT y hasta 8000 mensajes al día. Cada suscripción a Azure puede crear un centro de IoT en el nivel gratis.

Si está trabajando con un inicio rápido de flujos de dispositivo de IoT Hub, seleccione el nivel gratuito.

* Unidades de IoT Hub: El número de mensajes que se permiten por unidad al día depende del plan de tarifa del centro. Por ejemplo, si quiere que el Centro de IoT admita la entrada de 700 000 mensajes, seleccione dos unidades del nivel S1.

* Defender para IoT Actívelo para agregar un nivel adicional de protección ante amenazas en IoT y en los dispositivos. Esta opción no está disponible para los centros de conectividad del nivel gratuito.

* Configuración avanzada > Particiones del dispositivo a la nube: esta propiedad relaciona los mensajes del dispositivo a la nube con el número de lectores simultáneos de los mensajes. La mayoría de los centros solo necesitan cuatro particiones.

7. Seleccione Siguiente: Etiquetas para pasar a la pantalla siguiente.

Las etiquetas son pares nombre-valor. Puede asignar la misma etiqueta a varios recursos y grupos de recursos para clasificar los recursos y consolidar la facturación.

8. Seleccione Siguiente: Revisar y crear para revisar sus selecciones. Verá algo parecido a esta pantalla, pero con los valores que ha seleccionado al crear el centro.

9. Seleccione Crear para crear un centro. Esta operación tarda unos minutos.

