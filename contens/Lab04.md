# Connect an IoT Device to Azure

**Conecte un dispositivo de IoT a Azure**
**Escenario de laboratorio**
Contoso es conocido por producir quesos de alta calidad. Debido al rápido crecimiento de la empresa tanto en popularidad como en ventas, quieren tomar medidas para garantizar que sus quesos se mantengan en el mismo alto nivel de calidad que esperan sus clientes.

En el pasado, los trabajadores de la fábrica recopilaban datos de temperatura y humedad durante cada turno de trabajo. A la compañía le preocupa que las expansiones de la fábrica requieran un mayor monitoreo a medida que las nuevas instalaciones entren en funcionamiento y que un proceso manual para recopilar datos no se amplíe.

Contoso ha decidido lanzar un sistema automatizado que usa dispositivos IoT para monitorear la temperatura y la humedad. La velocidad a la que se comunican los datos de telemetría será ajustable para ayudar a garantizar que su proceso de fabricación esté bajo control a medida que los lotes de queso avanzan a través de procesos ambientalmente sensibles.

Para evaluar esta solución de monitoreo de activos antes de la implementación a gran escala, conectará un dispositivo IoT (que incluye sensores de temperatura y humedad) a IoT Hub.

> Nota: Para los propósitos de este laboratorio, creará una aplicación de consola .NET Core que simula el dispositivo y los sensores de IoT físicos. Su dispositivo simulado implementará el SDK de dispositivos de IoT y se conectará a IoT Hub como lo haría un dispositivo físico. Su dispositivo simulado también comunicará valores de telemetría utilizando los mismos recursos SDK utilizados por un dispositivo físico, pero las lecturas del sensor serán valores generados en lugar de valores reales leídos de los sensores de temperatura y humedad.

Los siguientes recursos serán creados:

![](LAB_AK_04-architecture.png)

**En este laboratorio**
En este laboratorio, comenzará por revisar los requisitos previos del laboratorio y ejecutará un script si es necesario para asegurarse de que su suscripción de Azure incluye los recursos necesarios. Luego, usará Azure Portal para registrar un ID de dispositivo con Azure IoT Hub y desarrollar la aplicación de dispositivo simulado correspondiente en Visual Studio Code. Luego, insertará la cadena de conexión (creada por IoT Hub cuando registró el dispositivo) en el código de su dispositivo simulado y ejecutará la aplicación para probar la conexión y verificar que la telemetría llegue a IoT Hub según lo previsto. El laboratorio incluye los siguientes ejercicios:

- Verificar los requisitos previos del laboratorio
- Crear un Azure IoT Hub Device ID mediante Azure Portal
- Crear y probar un dispositivo simulado (C #)

[back](../Readme.md)

































IoT Device Connection string 

```
HostName=iot-az220-training-bmvb.azure-devices.net;DeviceId=sensor-th-0001;SharedAccessKey=04V6/qXKdwUWCHJWKfo7Z/qgBXPlWyWRjYAz5X0C5vM=
```

