# Set up the Development Environment

## Escenario de laboratorio

Como uno de los desarrolladores de Contoso, sabe que configurar su entorno de desarrollo es un paso importante antes de comenzar a construir su solución Azure IoT. También sabe que Microsoft y otras empresas proporcionan una serie de herramientas que se pueden utilizar para desarrollar y respaldar sus soluciones de IoT, y que se deben tomar algunas decisiones sobre qué herramientas utilizará su equipo.

Decide preparar un entorno de desarrollo que el equipo pueda utilizar para trabajar en su solución de IoT. El entorno deberá respaldar su trabajo en Azure y en su PC local. Después de un poco de discusión, su equipo ha tomado las siguientes decisiones de alto nivel sobre el entorno de desarrollo:

Sistema operativo: 

Se utilizará Windows 10 como sistema operativo. La mayor parte de su equipo usa Windows, por lo que fue una elección lógica. Le indica al equipo que los servicios de Azure son compatibles con otros sistemas operativos (como Mac OS y Linux) y que Microsoft proporciona documentación de respaldo para los miembros de su equipo que eligen una de estas alternativas.
Herramientas de codificación generales: 

Visual Studio Code y la CLI de Azure se utilizarán como herramientas de codificación principales. Ambas herramientas admiten extensiones para IoT que aprovechan los SDK de Azure IoT.

Herramientas de IoT Edge: 

Docker Desktop Community y Python se utilizarán para admitir el desarrollo de módulos personalizados de IoT Edge (junto con Visual Studio Code).

Para respaldar estas decisiones, configurará el siguiente entorno:

1. Windows 10 de 64 bits: 

- Pro, Enterprise o Education (compilación 15063 o posterior). 
- 4GB - 8GB de RAM del sistema (cuanto más alto, mejor para Docker)
- Las características de Hyper-V y Containers de Windows deben estar habilitadas.
- El soporte de virtualización de hardware a nivel de BIOS debe estar habilitado en la configuración del BIOS.

> Nota: Al configurar el entorno de desarrollo en una máquina virtual, el entorno de VM debe admitir la virtualización anidada: virtualización anidada

1. CLI de Azure (actual / más reciente)
2. SDK de .NET Core 3.1.200 (o posterior)
3. VS Code (más reciente)
4. Python 3.9
5. Docker Desktop Community 2.1.0.5 (o posterior) configurado en Contenedores de Linux
6. Extensiones de IoT para VS Code y Azure CLI
7. node.js (más reciente)

> Nota: Se ha creado una máquina virtual para este curso que proporciona la mayoría de las herramientas especificadas anteriormente. Las instrucciones a continuación admiten el uso de la máquina virtual preparada o la configuración del entorno de desarrollo localmente usando su PC.

## En este laboratorio

En este laboratorio, configurará las herramientas de desarrollo básicas para su entorno de desarrollo, instalará las extensiones de Azure IoT para Visual Studio Code y la CLI de Azure, y luego descargará algunos archivos de GitHub que usará durante los laboratorios. 

El laboratorio incluye los siguientes ejercicios:

- Instalar herramientas y productos para desarrolladores
- Instalar extensiones de herramientas de desarrollo
- Configurar archivos de Course Lab y herramientas alternativas

[back](../Readme.md)