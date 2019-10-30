Creación y uso de una máquina virtual como entorno de desarrollo usando Vagrant y Docker
*************************************************************************************************

Este repo contiene las instrucciones y demás archivos requeridos para la creación, configuración
y uso de una máquina virtual basada en Vagrant que permite la ejecución de contendores de Docker.


Contenido
-------------------------------------------------------------------------------------------------

* Parte 1: Creación de la máquina virtual usando Vagrant.


* Parte 2: Encendido, apagado y borrado de la máquina virtual.


* Parte 3: Instalación y uso de las extensiones de VS code.


* Parte 4: Descarga de las imágenes desde Docker Hub.


* Parte 5: Ejecución de una imagen


* Resumen


* Material complementario



Parte 1: Creación de la máquina virtual usando Vagrant
-------------------------------------------------------------------------------------------------

En esta práctica se realizará la configuración de un ambiente de
programación portable que garantice una ejecución idéntica en todos los
computadores independientemente del tipo de sistema operativo y su versión.
    
**Advertencia**. Este laboratorio debe ser realizado por fuera del campus
de la Universidad, ya que el proxy bloquea algunos de los sitios requeridos 
para la instalación de la máquina virtual.
  

Creación de la máquina virtual
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Paso 1
  Descargue e instale `VirtualBox  <https://www.virtualbox.org/wiki/Downloads>`_.

Paso 2
  Descargue e instale `Vagrant <https://www.vagrantup.com/downloads.html>`_. de la forma habitual. 
  
  
  **Pasos exclusivos para Microsoft Windows**:

  Paso 2.1
     Abra la busqueda de Windows, escriba la palabra **variables** y escoja
     la opción **Editar las variables de entorno del sistema**.

  Paso 2.2
     Haga click en la opción **Variables de entorno...** ubicada en la
     parte inferior derecha.

  Paso 2.3
     Una vez dentro del módulo de edición, ubique la variable **Path**
     ubicada en la ventana **variables del sistema** en la parte inferior,
     señalela y haga click en **Editar**.

  Paso 2.4
     Verifique que en la definicion de la variable **Path**
     aparezca la declaración

     .. code-block:: bash
    
        %SYSTEMROOT%\System32\WindowsPowerShell\v1.0\

     Si no se encuentra incluida, haga click en **Nuevo** y agréguela.

Paso 3
  Instale el plugin para modificar el tamaño en disco de la máquina virtua. En
  el Terminal (o símbolo del sistema) ejecute
  
  .. code-block:: bash
  
     vagrant plugin install vagrant-disksize

Paso 4
  Clone este repositorio en su disco duro. En la página
  principal del repositorio encontrará el botón **Clone or download**.
  Renombre la carpeta. Esta será su carpeta de trabajo.

  .. image:: assets/fig-01.jpg
    :width: 400
    :alt: Alternative text

Paso 5
  Habra el Terminal y vaya a la carpeta que contiene la copia de este repositorio. 

Paso 6
  Proceda con el encendido de la máquina de acuerdo a su sistema operativo. Las 
  instrucciones detalladas aparecen más adelante en este mismo documento. 


Solución de problemas
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**1. Mi computador reporta que el Bios no permite activar la multitarea.**

Entre al Bios de su máquina y haga los cambios necesarios. Busque en Google el tipo particular de problema.


**2. Windows no permite activar la multitarea (Hyper V)**.

Realice el siguiente procedimiento:


Paso a)
  Digite la tecla de windows + x. Luego escoja la opción **Aplicaciones y características**.

Paso b)
  En el costado superior derecho, escoja la opción **Programas y características**. Se abrirá una nueva ventana emergente.

Paso c)
  Haga click en la opción **Activar o Desactivar las características de Windows** ubicada en la 
  parte superior izquierda, busque en la lista la aplicación **Hyper V** y desmárquela.



Parte 2: Encendido, apagado y borrado de la máquina virtual
-------------------------------------------------------------------------------------------------

En esta sección se describe el uso de la máquina virtual. Los comandos 
presentados a continuación se ejecutan en la interfaz de línea
de comandos (CLI) o prompt del sistema o Terminal. 

Los siguientes son videos explicativos del encendido de la máquina:

* Mac OS: https://youtu.be/RBfeiqcDcGk
* Windows: https://youtu.be/4vvJOzFFrcQ

Apertura del Terminal
  Para acceder al terminal de comandos haga lo siguiente:

* En Mac OS X, digite `Cmd + Space` para acceder a Spotligth, digite
  `terminal` y finalmente `Enter`.
* En Ubuntu, digite  `Ctrl + Alt + T`.
* En Windows, abra **ejecutar** y digite `cmd`.


Encendido
  Abra el Terminal y vaya hasta la carpeta donde clono este repositorio. Ejecute

  .. code-block:: bash

    vagrant up

  para enceder la VM en el background. Si la VM no ha sido creada,
  Vagrant la creara y configurará por usted.


Apertura de una sesión
  Después de encender la VM,  conéctese a ella con

  .. code-block:: bash

    vagrant ssh

  como resultado, el prompt cambiará a

  .. code-block:: bash

    Welcome to Ubuntu 18.04.1 LTS (GNU/Linux 4.15.0-42-generic x86_64)

      * Documentation:  https://help.ubuntu.com
      * Management:     https://landscape.canonical.com
      * Support:        https://ubuntu.com/advantage

    System information as of Sun Dec 16 01:56:16 UTC 2018

    System load:  0.41              Processes:             99
    Usage of /:   17.5% of 9.63GB   Users logged in:       0
    Memory usage: 16%               IP address for enp0s3: 10.0.2.15
    Swap usage:   0%


    Get cloud support with Ubuntu Advantage Cloud Guest:
      http://www.ubuntu.com/business/services/cloud

    0 packages can be updated.
    0 updates are security updates.

    Last login: Sun Dec 16 01:48:19 2018 from 10.0.2.2
    vagrant@ubuntu-bionic:~$

  En este prompt, usted podrá ejecutar comandos de Unix dentro de la VM.

Acceso a la carpeta compartida
  Para ir a la carpeta compartida entre la VM y su sistema
  operativo, ejecute

  .. code-block:: bash

    cd /vagrant

  .. important:: La carpeta donde clono este  repositorio y `/vagrant` comparten 
     la misma ubicación física en su disco duro. Los cambios que realice en un directorio 
     en un sistema operativo se refrejarán en el otro sistema operativo.

Cierre de sesión y retorno a la máquina local
  Para retornar a la sesión en su computador desde la VM ejecute

  .. code-block:: bash

    exit

  Este comando no apaga la máquina virtual (ella continua ejecutandose en el background).


Apagado de la VM
  Para apagar la VM ejecute

  .. code-block:: bash

    vagrant halt

  Para encender la VM nuevamente, deberá usar nuevamente

.. code-block:: bash

  vagrant up

Borrado de la VM
  Si por alguna razón requiere borrar la máquina virtual de su disco duro,
  habrá el Terminal y vaya a la carpeta donde está el archivo `Vagrantfile`.
  Luego ejecute

  .. code-block:: bash

    vagrant destroy



Parte 3: Instalación y uso de las extensiones de VS code
-------------------------------------------------------------------------------------------------

Paso 1
  Instale la extensión de desarrollo remoto (https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)


Paso 2
  Abra el Terminal y vaya hasta la carpeta donde clono este repositorio. Ejecute

  .. code-block:: bash

    vagrant up

  para enceder la VM en el background.


Paso 3
  En Terminal ejecute el comando `vagrant ssh-config` para obtener la configuración de la conexión.

  .. code-block:: bash

    $ vagrant ssh-config
    Host default
      HostName 127.0.0.1
      User vagrant
      Port 2222
      UserKnownHostsFile /dev/null
      StrictHostKeyChecking no
      PasswordAuthentication no
      IdentityFile /Volumes/GitHub/vagrant4docker/.vagrant/machines/default/virtualbox/private_key
      IdentitiesOnly yes
      LogLevel FATAL

  En la línea `IdentifyFile`  aparecera la ubicación de su configuración particular.


Paso 4
  En Visual Studio Code (VScode) haga click en el ícono `Remote Explorer`.

  .. image:: assets/fig-02.jpg
    :alt: fig-02  


Paso 5
  Haga click en  `SSH TARGETS` y luego en el símbolo de `+`. 
  
  .. image:: assets/fig-03.jpg
    :alt: fig-03


Paso 6
  En el comando de conexión digite `ssh vagrant4docker`. 
  
  .. image:: assets/fig-04.jpg
    :alt: fig-04  


Paso 7
  El sistema le solicitará que indique cual archivo de configuración desea modificar. Use el suyo por defecto.
      
  .. image:: assets/fig-05.jpg
    :alt: fig-05


Paso 8 
  Haga click en el ícono de configuración (el piñon) y luego seleccine nuevamente su archivo de  
  configuración. Se abrirá un editor de texto con la información de la configuración.

  .. image:: assets/fig-06.jpg
    :width: 400
    :alt: fig-06


Paso 9
  Edite la configuración, pegando la salida del comando `vagrant ssh-config`. Guarde el archivo.

  .. image:: assets/fig-07.jpg
    :width: 400
    :alt: fig-07


  .. image:: assets/fig-08.jpg
      :width: 400
      :alt: fig-08


Paso 10
  Para conectarse desde VScode a la máquina virtual, haga click en el ícono ubicado al frente del
  nombre de la conexión.

  .. image:: assets/fig-09.jpg
    :width: 400
    :alt: fig-09

 
  En este momento, VScode debe estar conectado a la máquina virtual como si fuera la máquina loca. 

  .. image:: assets/fig-10.jpg
    :width: 400
    :alt: fig-10

Paso 11
  Instale el complemento de Docker de Microsoft. 



Parte 4: Descarga de las imágenes desde Docker Hub.
-------------------------------------------------------------------------------------------------

Antes de ejecutar una imágen es preferible realizar su descarga a la máquina virtual. Para ello:

1.  Cree una cuenta de usuario en Docker Hub (https://hub.docker.com)

2.  Descargue una o más imágenes de Docker, tal como se indica a continuación.

Encendido de la máquina virtual
  Abra el Terminal y vaya hasta la carpeta donde clono este repositorio. Ejecute

  .. code-block:: bash

    vagrant up 


Apertura de una sesión
  Después de encender la VM,  conéctese a ella con

  .. code-block:: bash

    vagrant ssh

Acceso a la carpeta compartida
  Para ir a la carpeta compartida entre la VM y su sistema
  operativo, ejecute

  .. code-block:: bash

    cd /vagrant

  En esta carpeta ejecuta la instrucción correspondiente para iniciar alguna de las 
  aplicaciones listadas a continnuación.


Login en Docker Hub
  Acceda a Docker Hub desde la consola con el siguiente comando:

  .. code-block:: bash

    docker login

Descarga de las imágenes
  Descarge las imágenes que requiera usando el comando indicado.

  * Python 3
  
    .. code-block::

      vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/python:3.7
            
  * Apache Pig
  
    .. code-block::

        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/pig:0.18.0

  * Apache Mahout
  
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/mahout:0.14.0

  * Apache Hive
  
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/hive:2.3.5
  
  
  * Apache Spark
  
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/spark:2.4.3
    
  
  * Open Refine
  
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/openrefine:3.2

  * Apache Superset
  
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/superset:0.34.0


3. Use las imágenes y continue su trabajo. O finalice su trabajo apagando la máquina virtual. 
   La ejecución de las imágenes puede realizarse desde VS code o desde el Terminal, tal como 
   se indica en las siguientes partes de la documentación.




Parte 5: Ejecución de una imagen
-------------------------------------------------------------------------------------------------

Las imágenes pueden ser ejecutadas directamente desd el Terminal o desde VS code.


Ejecución de una imagen desde el Terminal usando docker-compose
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`docker-compose` puede ser usado para ejecutar una imágen como un servicio de acuerdo con los 
parámetros predefinidos en un archivo de configuración

Encendido de la máquina virtual
  Abra el Terminal y vaya hasta la carpeta donde clono este repositorio. Ejecute

  .. code-block:: bash

    vagrant up 


Apertura de una sesión
  Después de encender la VM,  conéctese a ella con

  .. code-block:: bash

    vagrant ssh

Acceso a la carpeta compartida
  Para ir a la carpeta compartida entre la VM y su sistema
  operativo, ejecute

  .. code-block:: bash

    cd /vagrant
  
  En esta carpeta ejecuta la instrucción correspondiente para iniciar alguna de las 
  aplicaciones listadas a continnuación.

Ejecución de la imagen
  Ejecute el imagen con:

  .. code-block:: bash

    docker-compose --file yml/NOMBRE.yml up

  donde `NOMBRE` es el nombre del archivo. Por ejemplo, para ejecutar Apache Pig use:

  .. code-block:: bash

    docker-compose --file yml/pig.yml up


Ejecución de una imagen usando VS code
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Una vez haya conectado VS code de forma remota a la máquina virtual y haya instalado el 
complemento de Docker, usted podrá visualizar las imágenes descargadas la máquina virtual.


Para ejecutar una imagen:


1. Haga click en el ícono de Docker en la barra vertical de la parte derecha de VS code.

2. Haga click en el menu `IMAGES` y luego en la imagen correspondiente para ver los tags 
   disponibles.

3. Haga click en el boton derecho sobre el tag y seleccione `Run interactive`.  

  .. image:: assets/fig-11.png
    :alt: fig-11






Resumen
-------------------------------------------------------------------------------------------------

.. code-block:: bash

  ## Encender la VM
  vagrant up

  ## Apagar la VM
  vagrant halt

  ## Borrar la VM
  vagrant destroy

  ## Abrir una sesión en la VM
  vagrant ssh

  ## Cerrar la sesión en la VM
  exit


  ## Ejecución de programas desde el Terminal
  
  docker-compose --file yml/jupyterlab.yml up
  
  docker-compose --file yml/pig.yml up
  
  docker-compose --file yml/mahout.yml up
  
  docker-compose --file yml/hive.yml up
  
  docker-compose --file yml/superset.yml up
  
  docker-compose --file yml/pyspark.yml up
  
  docker-compose --file yml/openrefine.yml up


  

Material complementario
-------------------------------------------------------------------------------------------------

* `What is Vagrant? <https://www.vagrantup.com/intro/index.html>`_

* `Getting Started <https://www.vagrantup.com/intro/getting-started/index.html>`_.

* `Puppet Apply Provisiner <https://www.vagrantup.com/docs/provisioning/puppet_apply.html>`_.

* `Docker tutorial <https://docs.docker.com/get-started/>`_.
