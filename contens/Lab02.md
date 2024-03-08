# Getting Started with Azure IoT Services

**Introducción a los servicios de Azure IoT**
**Escenario de laboratorio**
Su rol en este laboratorio es el de un desarrollador de Azure IoT que trabaja para Contoso, una empresa que elabora y distribuye quesos gourmet.

Se le ha asignado la tarea de explorar Azure y los servicios de Azure IoT que utilizará para desarrollar la solución de IoT de Contoso. Ya se ha familiarizado con Azure Portal y ha creado un grupo de recursos para su proyecto. Ahora debe comenzar a investigar los servicios de Azure IoT.

**En este laboratorio**
En este laboratorio, creará y examinará **Azure IoT Hub** y un servicio de aprovisionamiento de dispositivos de IoT Hub (**IoT Hub Device Provisioning Service**). El laboratorio incluye los siguientes ejercicios:

- Explore los requisitos de nombres de recursos únicos a nivel mundial
- Crear un IoT Hub con Azure Portal
- Examinar las características del servicio IoT Hub
- Cree un servicio de aprovisionamiento de dispositivos (IoT Hub Device Provisioning Service) y vincúlelarlo a su IoT Hub
- Examinar las funciones del servicio de aprovisionamiento de dispositivos

### Exercise 1: Explore Globally Unique Resource Naming Requirements

En los laboratorios 2 a 19 de este curso, creará recursos de Azure que se utilizarán para desarrollar su solución de IoT. Para garantizar la coherencia entre los laboratorios y ayudar a ordenar los recursos cuando haya terminado con ellos, se proporcionarán nombres de recursos sugeridos dentro de las instrucciones del laboratorio. En la medida de lo posible, los nombres de recursos sugeridos seguirán las pautas de nomenclatura recomendadas aquí: 

[Desarrollo de la estrategia de nomenclatura y etiquetado de los recursos de Azure - Cloud Adoption Framework | Microsoft Docs](https://docs.microsoft.com/es-es/azure/cloud-adoption-framework/ready/azure-best-practices/naming-and-tagging)

Sin embargo, muchos de los recursos que creará durante este curso exponen servicios que se pueden consumir en la web, lo que significa que deben tener nombres únicos a nivel mundial. Para asegurarse de que estos recursos satisfagan el requisito de exclusividad global, agregará un identificador exclusivo al final de los nombres de los recursos cuando sea necesario.

En este ejercicio, creará su identificación única y revisará algunos ejemplos que ayudarán a ilustrar cómo utilizará su identificación única durante las prácticas de laboratorio 2 a 19 de este curso.

[back](../Readme.md)