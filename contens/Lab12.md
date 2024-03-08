# Setup an IoT Edge Gateway

**Configurar una puerta de enlace de IoT Edge**

## Escenario de laboratorio

Este laboratorio es teórico y lo guiará a través de cómo se puede usar un dispositivo IoT Edge como puerta de enlace.

Hay tres patrones para usar un dispositivo IoT Edge como puerta de enlace: transparente, traducción de protocolo y traducción de identidad:

**Transparente:** los dispositivos que teóricamente podrían conectarse a IoT Hub pueden conectarse a un dispositivo de puerta de enlace. Los dispositivos posteriores tienen sus propias identidades de IoT Hub y utilizan cualquiera de los protocolos MQTT, AMQP o HTTP. La puerta de enlace simplemente pasa las comunicaciones entre los dispositivos y IoT Hub. Los dispositivos no saben que se están comunicando con la nube a través de una puerta de enlace, y un usuario que interactúa con los dispositivos en IoT Hub no conoce el dispositivo de puerta de enlace intermedio. Por tanto, la pasarela es transparente. 

**Traducción de protocolo:** también conocido como patrón de puerta de enlace opaco, los dispositivos que no son compatibles con MQTT, AMQP o HTTP pueden usar un dispositivo de puerta de enlace para enviar datos a IoT Hub en su nombre. La puerta de enlace comprende el protocolo utilizado por los dispositivos posteriores y es el único dispositivo que tiene una identidad en IoT Hub. Toda la información parece provenir de un dispositivo, la puerta de enlace. Los dispositivos posteriores deben incorporar información de identificación adicional en sus mensajes si las aplicaciones en la nube desean analizar los datos por dispositivo. Además, las primitivas de IoT Hub, como los gemelos y los métodos, solo están disponibles para el dispositivo de puerta de enlace, no para los dispositivos posteriores.

**Traducción de identidad:** los dispositivos que no pueden conectarse a IoT Hub pueden conectarse a un dispositivo de puerta de enlace, en su lugar. La puerta de enlace proporciona la traducción de la identidad y el protocolo de IoT Hub en nombre de los dispositivos posteriores. La puerta de enlace es lo suficientemente inteligente como para comprender el protocolo utilizado por los dispositivos descendentes, proporcionarles identidad y traduce las primitivas de IoT Hub. Los dispositivos posteriores aparecen en IoT Hub como dispositivos de primera clase con gemelos y métodos. Un usuario puede interactuar con los dispositivos en IoT Hub y desconoce el dispositivo de puerta de enlace intermedio.

**Se crearán los siguientes recursos:**

![](LAB_AK_12-architecture.png)

## En este laboratorio

**En este laboratorio, completará las siguientes actividades:**

- Verifique que se cumplan los requisitos previos del laboratorio (que tenga los recursos de Azure necesarios)
- Implementar una máquina virtual Linux habilitada para Azure IoT Edge como un dispositivo IoT Edge
- Generar y configurar certificados CA de dispositivos IoT Edge
- Cree una identidad de dispositivo de IoT Edge en IoT Hub mediante Azure Portal
- Configurar el nombre de host de la puerta de enlace de IoT Edge
- Conectar un dispositivo de puerta de enlace de IoT Edge a IoT Hub
- Puertos de dispositivo de puerta de enlace de IoT Edge abiertos para la comunicación
- Cree la identidad del dispositivo en sentido descendente en IoT Hub
- Conectar un dispositivo downstream a IoT Edge Gateway
- Verificar el flujo de eventos

[back](../Readme.md)



IoT Edge Device like vm connection string

```
HostName=iot-az220-training-bmvb.azure-devices.net;DeviceId=vm-az220-training-gw0001-bmvb;SharedAccessKey=hu2177Vd7rV2/To8QZym4ECAMHEua8vE6m9J62tD++U=
P455w0rd.rd2022
```

cd ..full DNS name of vm

```
vm-az220-training-gw0001-bmvb.westeurope.cloudapp.azure.com
```

sensor-th-0072 connection string

```
HostName=iot-az220-training-bmvb.azure-devices.net;DeviceId=sensor-th-0072;SharedAccessKey=L4HChA38V0VO3IECrpfANuCk+/L9+0Ke8sEn32FfW9k=
```

sensor-th-0072 connection string with gatewayhostname added:

```
 HostName=<IoT-Hub-Name>.azure-devices.net;DeviceId=sensor-th-0072;SharedAccessKey=<Primary-Key-for-IoT-Device>;GatewayHostName=<DNS-Name-for-IoT-Edge-Device>
```

```
HostName=iot-az220-training-{}.azure-devices.net;DeviceId={};SharedAccessKey={};GatewayHostName={}
```

```
scp -r -p manager@52.234.225.181:/tmp/lab12 .
```

