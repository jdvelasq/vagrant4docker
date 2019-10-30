Creación y uso de una máquina virtual como entorno de desarrollo usando Vagrant y Docker
*************************************************************************************************

Este repo contiene las instrucciones y demás archivos requeridos para la creación, configuración
y uso de una máquina virtual basada en Vagrant que permite la ejecución de contendores de Docker.


Contenido
-------------------------------------------------------------------------------------------------

* Parte 1: Creación de la máquina virtual usando Vagrant.

* Parte 2: Encendido, apagado y borrado de la máquina virtual.

* Parte 3: Instalación y uso de las extensiones de VS code.



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


**Solución de problemas**

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














* [Parte 1. Creación de la máquina virtual ](tutorial/parte-1-creacion-vm.rst)

* [Parte 2. Encendido y apagado de la máquina virtual](tutorial/parte-2-encendido-apagado-vm.rst)

* [Parte 3. Conexión remote de VS code con la máquina virtual](tutorial/parte-3-conexion-vscode.rst)

* [Parte 4. Descarga de imágenes de Docker](tutorial/parte-4-descarga-imagenes.rst)

* [Parte 5. Ejecución de imágenes de Docker](tutorial/parte-5-ejecucion-imagenes.rst)


Resumen
=================================================================================================

```bash 

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
```  
  

Material complementario
========================================

* `What is Vagrant? <https://www.vagrantup.com/intro/index.html>`_

* `Getting Started <https://www.vagrantup.com/intro/getting-started/index.html>`_.

* `Puppet Apply Provisiner <https://www.vagrantup.com/docs/provisioning/puppet_apply.html>`_.

* `Docker tutorial <https://docs.docker.com/get-started/>`_.
