# Develop, Deploy, and debug a custom module on Azure IoT Edge with VS Code

**Desarrolle, implemente y depure un módulo personalizado en Azure IoT Edge con VS Code**

## Escenario de laboratorio

Para ayudar a administrar las fluctuaciones en la demanda de los consumidores, Contoso mantiene un pequeño inventario de ruedas de queso madurado en un almacén en cada instalación de fabricación de queso. Estas ruedas maduras están selladas con cera y el entorno de almacenamiento se controla cuidadosamente para garantizar que el queso permanezca en perfectas condiciones. Contoso utiliza un sistema transportador para mover las grandes ruedas de queso selladas con cera desde el almacén hasta las instalaciones de empaque.

En el pasado, Contoso ha ejecutado su proceso de empaquetado a plena capacidad, procesando todo el queso que se coloca en el sistema. Cualquier exceso de volumen de queso envasado no era un problema porque podía utilizarse para ofertas promocionales y podía extraerse queso adicional del inventario según fuera necesario. Sin embargo, con el crecimiento significativo que está experimentando Contoso y con las crecientes fluctuaciones debido a la demanda mundial, la empresa necesita automatizar el sistema de una manera que ayude a administrar el volumen de queso que se empaqueta.

Dado que ya implementó la solución de IoT que monitorea el sistema de cinta transportadora en el área de empaque y envío, se le asignó la tarea de desarrollar una solución que ayude a administrar / controlar los volúmenes de empaque.

Para asegurarse de que se haya procesado la cantidad correcta de paquetes, decide crear (e implementar en un dispositivo IoT Edge) un módulo simple que cuenta la cantidad de paquetes detectados en el sistema de cinta transportadora. Ya tiene otro módulo disponible que se puede usar para detectar los paquetes (ambos módulos se implementarán en el mismo dispositivo IoT Edge).

Debe crear e implementar un módulo de IoT Edge personalizado que cuente la cantidad de paquetes detectados por el otro módulo.

Este laboratorio incluye los siguientes requisitos previos para la máquina de desarrollo (entorno de host del laboratorio: VM o PC):

- Visual Studio Code con las siguientes extensiones instaladas:

- Herramientas de Azure IoT de Microsoft ([Standalone Azure IoT EdgeHub Dev Tool (iotedgehubdev) Introduction - IoT Developer (microsoft.com)](https://devblogs.microsoft.com/iotdev/standalone-azure-iot-edgehub-dev-tool-iotedgehubdev-introduction/))

  [iotedgehubdev · PyPI](https://pypi.org/project/iotedgehubdev/)

  [Desarrollo y depuración de módulos para Azure IoT Edge | Microsoft Docs](https://docs.microsoft.com/es-es/azure/iot-edge/how-to-vs-code-develop-module?view=iotedge-2020-11)

- C # de Microsoft

- Docker

Docker Community Edition instalado en la máquina de desarrollo, con Docker Client versión 18.03.0 o posterior

- Descarga Docker Desktop para Mac y Windows

> Importante: debido a la eliminación del 13 de enero de 2020 de la compatibilidad con Azure Container Registry para cualquier versión de TLS anterior a la versión 1.2 de TLS, debe ejecutar Docker Client 18.03.0 o posterior.

**Se crearán los siguientes recursos:**

![](LAB_AK_13-architecture.png)

## En este laboratorio

**En este laboratorio, completará las siguientes actividades:**

- Verifique que se cumplan los requisitos previos del laboratorio (que tenga los recursos de Azure necesarios)
- Crear el registro de contenedores
- Crea y personalizar un módulo Edge
- Implementar módulos en el dispositivo Edge

[back](../Readme.md)

Python power shell execution

```

```

Exercise 2.4

pip installing iotedgehubdev

```
 
```

Azure Container register (Login server)

```

```

ACR (Username and password)

```

```

```

```

Connec to ACR from command powershell line

```

```

Connection string of polyName IoThubOwner

```

```

Exercise 5 task 4

Start in docker the conteiner to keep the debug (BEFORE debugging)

Exercise 6 task 4 Para la publicación

También el el fichero `.env` deberá quedar así sincronizado con el fichero `deployment.template.json`

````
CONTAINER_REGISTRY_USERNAME_{ACR}={ACR}username
CONTAINER_REGISTRY_PASSWORD_{ACR}b={ACR}password
````

Lineas 14,15 y 16 del deployment.template.json:

```json
"username": "$CONTAINER_REGISTRY_USERNAME_{ACR}",
"password": "$CONTAINER_REGISTRY_PASSWORD_a{ACR}",
"address": "{ACR}.azurecr.io"
```

En el fichero module.json en el repository (linea 5) para la publicación

```
{ACR}.azurecr.io/objectbcountingmodule
acraz220trainingbmvb.azurecr.io/objectbcountingmodule
```

Resultado en ACR repository + tag

```
objectbcountingmodule:0.0.1-amd64
```

info: Client connected
info: app listening on 3000
info: Time: 1644579163425 POST /api/v1/messages
info: Send message successfullly
info: [Print] hello world
info: Time: 1644579211058 POST /api/v1/messages
info: Send message successfullly
info: [Print] hello world
