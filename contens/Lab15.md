# Remotely monitor and control devices with Azure IoT Hub

Supervisar y controlar dispositivos de forma remota con Azure IoT Hub
**Escenario de laboratorio**
Contoso se enorgullece de sus quesos galardonados y tiene cuidado de mantener la temperatura y la humedad perfectas durante todo el proceso de fabricación, pero las condiciones durante el proceso de envejecimiento siempre han recibido una atención especial.

En los últimos años, Contoso ha utilizado sensores ambientales para registrar las condiciones dentro de sus cuevas de queso natural donde ocurre el envejecimiento, y ha utilizado esos datos para identificar un entorno casi perfecto. Los datos de los lugares más exitosos (también conocidos como productores de premios) indican que la temperatura ideal para añejar el queso es de aproximadamente 50 grados Fahrenheit +/- 5 grados (10 grados Celsius +/- 2,8 grados). El valor de humedad ideal, medido en porcentaje de saturación máxima, es aproximadamente 85% +/- 10%.

Estos valores ideales de temperatura y humedad funcionan bien para la mayoría de los tipos de queso. Sin embargo, se requieren variaciones menores para quesos especialmente duros o especialmente blandos. El entorno también debe ajustarse en momentos / fases críticos dentro del proceso de envejecimiento para lograr resultados específicos, como una condición deseada para la corteza del queso.

Contoso tiene la suerte de operar cuevas de queso (en ciertas regiones geográficas) que naturalmente mantienen condiciones ideales casi todo el año. Sin embargo, incluso en estas ubicaciones, la gestión del medio ambiente durante el proceso de envejecimiento es fundamental. Además, las cuevas naturales a menudo tienen varias cámaras diferentes, cada una de las cuales puede tener un entorno ligeramente diferente. Las variedades de queso se colocan en una cámara (zona) que se adapta a sus requisitos específicos. Para mantener las condiciones ambientales dentro de los límites deseados, Contoso usa un sistema de procesamiento / acondicionamiento de aire que controla tanto la temperatura como la humedad.

Actualmente, un operador monitorea las condiciones ambientales dentro de cada zona de una instalación de cueva y ajusta la configuración del sistema de procesamiento de aire cuando es necesario para mantener la temperatura y la humedad deseadas. Los operadores pueden acceder a cada zona y verificar las condiciones ambientales cada 4 horas. En lugares donde la temperatura cambia drásticamente entre el máximo diurno y el mínimo nocturno, las condiciones pueden salirse de los límites deseados.

Contoso le ha asignado la tarea de implementar un sistema automatizado que mantenga el entorno de la cueva dentro de los límites de control.

En este laboratorio, creará un prototipo de un sistema de monitoreo de cueva de queso que implementa dispositivos de IoT. Cada dispositivo está equipado con sensores de temperatura y humedad, y está conectado al sistema de procesamiento de aire que controla la temperatura y la humedad de la zona donde se encuentra el dispositivo.

**Condiciones de laboratorio simplificadas**
La frecuencia de la salida de telemetría es una consideración importante en las soluciones de producción. Es posible que un sensor de temperatura en una unidad de refrigeración solo necesite informar una vez por minuto, mientras que un sensor de aceleración en una aeronave puede tener que informar diez veces por segundo. En algunos casos, la frecuencia a la que se debe enviar la telemetría depende de las condiciones actuales. Por ejemplo, si la temperatura en nuestro escenario de la cueva del queso tiende a bajar rápidamente por la noche, puede beneficiarse de tener lecturas de sensor más frecuentes a partir de dos horas antes del atardecer. Por supuesto, el requisito de cambiar la frecuencia de la telemetría no necesita ser parte de un patrón predecible, los eventos que impulsan nuestra necesidad de cambiar la configuración del dispositivo de IoT pueden ser impredecibles.

Para simplificar las cosas en este laboratorio, haremos las siguientes suposiciones:

- El dispositivo enviará telemetría (valores de temperatura y humedad) al IoT Hub cada pocos segundos. Aunque esta frecuencia no es realista para una cueva de queso, es ideal para un entorno de laboratorio cuando necesitamos ver cambios con frecuencia, no cada 15 minutos.

- El sistema de procesamiento de aire es un ventilador que puede estar en uno de tres estados: encendido, apagado o averiado.

  - El ventilador se inicializa al estado de apagado.

  - La energía eléctrica del ventilador se controla (encendido / apagado) mediante un método directo en el dispositivo IoT.

  - Los valores de propiedad deseados de Device Twin se utilizan para establecer el estado deseado del ventilador. Los valores de propiedad deseados anularán cualquier configuración predeterminada para el ventilador / dispositivo.

  - La temperatura se puede controlar encendiendo / apagando el ventilador (encender el ventilador bajará la temperatura)

La codificación en este laboratorio se divide en tres partes: envío y recepción de telemetría, invocación y ejecución de un método directo, configuración y lectura de las propiedades gemelas del dispositivo.

Comenzará escribiendo dos aplicaciones: una para que un dispositivo envíe telemetría y otra para un servicio de back-end (que se ejecutará en la nube) para recibir la telemetría.

Se crearán los siguientes recursos:

![](LAB_AK_15-architecture.png)

**En este laboratorio**
En este laboratorio, completará las siguientes actividades:

- Verificar que se cumplan los requisitos previos del laboratorio (que tenga los recursos de Azure necesarios)

- El script creará un IoT Hub si es necesario.
- El script creará una nueva identidad de dispositivo necesaria para este laboratorio.
- Crear una aplicación de dispositivo simulado para enviar telemetría de dispositivo a IoT Hub
- Crear una aplicación de servicio back-end para escuchar la telemetría
- Implementar un método directo para comunicar la configuración al dispositivo IoT
- Implementar la funcionalidad de dispositivos gemelos para administrar las propiedades de los dispositivos de IoT

[back](../Readme.md)



- deviceConnectionString (Primary connection string del sensor)

```

```

- devicePrimaryKey (Primary Key del sensor)

```

```

- eventHubsCompatibleEndpoint (En el IoT Hub es en Hub settings->Built-in Endpoing hasta antes del punto y coma de SharedAccessKey)

```
sb://iothub-ns-iot-az220-17561499-2b42dd39ae.servicebus.windows.net
```

- eventHubsCompatiblePath (Es el nombre del IoTHub
- )

```
iot-az220-training-bv11
```

- iotHubSasKey (IoTHub ->Shared access policies->service->PrimaryKey)

```
69A6e3LwAxHewk3JE3mEdo2EvXTojQJ0XKtaFeSKHt8=
```

- serviceConnectionString (IoTHub ->Shared access policies->iothubowner->PrimaryKey)

```
HostName=iot-az220-training-bv11.azure-devices.net;SharedAccessKeyName=iothubowner;SharedAccessKey=SGON/tMmsuDmtMdLBbNwsMKceW1XoG063q7Z41MbXc4=
```

```
HostName=iot-az220-training-bv11.azure-devices.net;SharedAccessKeyName=iothubowner;SharedAccessKey=SGON/tMmsuDmtMdLBbNwsMKceW1XoG063q7Z41MbXc4=
```



