# Lab 13 es tutorial

Referencia: [Develop Azure IoT Edge modules using Visual Studio Code tutorial | Microsoft Learn](https://learn.microsoft.com/en-us/azure/iot-edge/tutorial-develop-for-linux?view=iotedge-1.4&tabs=csharp&pivots=iotedge-dev-cli)

* **Login server**:acraz220trainingbvb20240312.azurecr.io
* **Username**: acraz220trainingbvb20240312
* **password**: <ACR password>

**Secuencia despues de crear el código:** (Debe estar docker desktop iniciado)

```
dotnet build

dotnet publish --os linux --arch x64 /t:PublishContainer --self-contained -c Release

docker tag filtermodule acraz220trainingbvb20240312.azurecr.io/filtermodule:0.0.2-amd64

docker push acraz220trainingbvb20240312.azurecr.io/filtermodule:0.0.2-amd64

docker login -u acraz220trainingbvb20240312 -p <ACR Password> acraz220trainingbvb20240312.azurecr.io

az acr login -n acraz220trainingbvb20240312.azurecr.io

az iot edge set-modules --hub-name iot-az220-training-bvb20240312 --device-id iotedgedev-edgedevice --content ./deployment.template.json --login "HostName=iot-az220-training-bvb20240312.azure-devices.net;SharedAccessKeyName=iothubowner;SharedAccessKey=<IoT Hub Primary Key for owner>"
```

**Rutas**

```
sensorTofiltermodule
FROM /messages/modules/tempSensor/outputs/temperatureOutput INTO BrokeredEndpoint("/modules/filtermodule/inputs/inputFromSensor")

filtermoduleToIoTHub
FROM /messages/modules/filtermodule/outputs/* INTO $upstream"
```

**Desplegar el IoT Edge Device con los dos módulos**

```
az iot edge set-modules --hub-name iot-az220-training-bvb20240312 --device-id iotedgedev-edgedevice --content ./deployment.template.json --login "HostName=iot-az220-training-bvb20240312.azure-devices.net;SharedAccessKeyName=iothubowner;SharedAccessKey=v<IoT Hub Primary Key for owner>"
```

**Comandos en el interior de la máquina virtual o dispositivo IoT Edge**

```bash
sudo iotedge system status              # Verificar el estado del runtime de IoT Edge
sudo iotedge check                      # Verificación de las comunicaciones del IoT Edge
sudo iotedge list                       # Listar módulos IoTEdge instalados y en ejecución
sudo iotedge logs <module_name> -f      # Ver los logs de un módulo IoT Edge específico
sudo iotedge restart <module_name>      # Reiniciar un módulo IoT Edge específico
sudo docker ps                          # Listar los contenedores Docker en ejecución
sudo docker stop <container_name>       # Detener un contenedor Docker en ejecución
sudo docker image list                  # Listar las imágenes Docker disponibles en el dispositivo IoT Edge
sudo docker container list              # Listar todos los contenedores Docker en el dispositivo IoT Edge
docker exec -it <container_id> /bin/bash# Acceder a la línea de comandos de un contenedor Docker en ejecución con shell Bash
docker exec -it <container_id> /bin/sh  # Acceder a la línea de comandos de un contenedor Docker en ejecución con shell sh
```

> **Nota:** Alguno de estos comandos deberán ser finalizados con **CTRL+C**

**Monitorizar IoT Hub**

` az iot hub monitor-events --hub-name <IoT hub Names>`

