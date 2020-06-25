# 1 Introducción
Una empresa multinacional desea establecerse físicamente en Costa Rica y construir un sitio web para compras en línea, con el objetivo de ofrecer a sus clientes la posibilidad de hacer sus pedidos en cualquier momento y desde cualquier lugar.

Actualmente está conformado por 3 sucursales, cada una de ellas son independiente con su tecnología (sistema operativos y motor de bases de datos). Cada una de las sucursales tiene su propia base de datos relacional, y en forma general debe proveer la estructura para almacenar productos, categoría, inventario, clientes, facturación, compras de productos y proveedores.

* * *

# 2 Preparación del entorno
Antes de iniciar el desarrollo es necesario conocer las herramientas y tecnologías necesarias para el desarrollo completo del proyecto. Y esto significa preparar un entorno donde pueda ser construida la solución. Dados los requisitos que deben ser cumplidos para logar el objetivo, se identificó software y conocimiento necesario para iniciar el proceso y desarrollar la aplicación desde scratch en nuestro ordenador.

### 2.1 Requisitos del sistema

  *   Docker Desktop containers.
  *   SQL Server 2017 o superior y Management Studio.
  *   Windows 10 pro. (Preferiblemente)
  *   Windows 10 Enterprise. (Opcionalmente)
  *   Tecnología hyper-v activada en el equipo.
  *   Virtualización activada.
  *   Distribución WSL de kernel de linux instalada en el equipo. (Solo si usa el GUI Docker Toolbox)
  *   Angular 9.*

### 2.2 Conocimiento necesario

  *   Bases de datos distribuidas.
  *   Protocolos de conectividad TCP/IP.
  *   Diagramas entidad relación.
  *   Desarrollo web.(Básico)
  *   Entorno de desarrollo angular 9.
  *   Apertura de reglas para I/O mediante puertos en el firewall y router.

### 2.3 Contenedores.
En esta sección se ecplica como preparar los contenedores. La preparación de los contenedores no requiere demasiado esfuerzo si se cumple con los requisitos del sistema, el primer paso es determinar la imagen de contenedor que va a ser utilizada, y como en este proyecto se utiliza sql server 2017 o superior se optó por una imagen preconstruida por microsoft.

**Paso 1. Instalar Docker**
El primer paso es instalar docker desktop. Esta aplicación puede ser descargada de la página principal
[Descargar Docker Desktop](https://www.docker.com/products/docker-desktop).

Una vez instalado y terminado el tutorial brindado por la aplicación, el cuál es escencial para comprender el funcionamiento básico de docker containers, se puede proceder a construir los contenedores con la imagen de sql server 2017.

**Paso 2. Montar la imagen de Sql Server**
Terminado el paso anterior, debemos abrir la consola de comando ```cmd```, presionando ```Inicio + R``` y en la ventana de Ejecutar se escribe 'cmd' y presiona ```Enter```.

Cuando la línea de comando inicie ingresamos lo siguiente:
```
docker run --name Particion1 -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Particion1" -e "MSSQL_PID=Express" -p 1434:1434 -d mcr.microsoft.com/mssql/server:2017-latest-ubuntu-latest
```
y presiona ```Enter```. La imagen se va a descargar y será construida automáticamente.
>Recuerda que para crear los otros contenedores debe repetir el _Paso 2_ y cambiar el nombre de Particion1 a Particion2 o 3, al igual que la contraseña.

>En la creación del primer contenedor deben ser utilizados los puertos 1434:1434, en el segundo contenedor debe ser 1435:1435 y en el tercero, 1436:1436.

El resultado de realizar estos pasos debe presentarse de la siguiente manera:

![Imagen 1: Comandos de doker](https://raw.githubusercontent.com/yerickcano/Empresa-Multinacional/master/Assets/docker-commands.PNG)

_**Información detallada de la imagen utilizada para el contenedor SQL SERVER de este proyecto:**_
[Imagen de Microsoft Sql Server Docker](https://hub.docker.com/_/microsoft-mssql-server).

### 2.4 Management Studio

# 4 Decisiones de diseño.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 5 Mock up.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 6 Diseño de la base de datos.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 7 Arquitectura.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 8 Base de datos.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 9 Página Web.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 10 Integración de FE y BE.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.

* * *

# 11 Documentación externa.
Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno estándar de las industrias desde el año 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido usó una galería de textos y los mezcló de tal manera que logró hacer un libro de textos especimen. No sólo sobrevivió 500 años, sino que tambien ingresó como texto de relleno en documentos electrónicos, quedando esencialmente igual al original. Fue popularizado en los 60s con la creación de las hojas "Letraset", las cuales contenian pasajes de Lorem Ipsum, y más recientemente con software de autoedición, como por ejemplo Aldus PageMaker, el cual incluye versiones de Lorem Ipsum.
