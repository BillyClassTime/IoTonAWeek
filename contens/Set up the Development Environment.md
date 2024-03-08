# Set up the Development Environment

Entorno de desarrollo:

1. Sistema operativo:

   Se utilizará Windows 10 como sistema operativo. La mayor parte de su equipo usa Windows, por lo que fue una elección lógica. Le indica al equipo que los servicios de Azure son compatibles con otros sistemas operativos (como Mac OS y Linux) y que Microsoft proporciona documentación de respaldo para los miembros de su equipo que eligen una de estas alternativas.

2. Herramientas de codificación generales: 

   Visual Studio Code y la CLI de Azure se utilizarán como herramientas de codificación principales. Ambas herramientas admiten extensiones para IoT que aprovechan los SDK de Azure IoT.

3. Herramientas de IoT Edge: 

   Docker Desktop Community y Python se utilizarán para admitir el desarrollo de módulos personalizados de IoT Edge (junto con Visual Studio Code).

Configurar el siguiente entorno:

1. Windows 10 de 64 bits: 

- Pro, Enterprise o Education (compilación 15063 o posterior). 
- 4GB - 8GB de RAM del sistema (cuanto más alto, mejor para Docker)
- Las características de Hyper-V y Containers de Windows deben estar habilitadas.
- El soporte de virtualización de hardware a nivel de BIOS debe estar habilitado en la configuración del BIOS.

> Nota: Al configurar el entorno de desarrollo en una máquina virtual, el entorno de VM debe admitir la virtualización anidada: virtualización anidada

3. CLI de Azure (actual / más reciente)
4. SDK de .NET Core 3.1.200 (o posterior)
5. VS Code (más reciente)
6. Python 3.9
7. Docker Desktop Community 2.1.0.5 (o posterior) configurado en Contenedores de Linux
8. Extensiones de IoT para VS Code y Azure CLI
9. node.js (más reciente)

