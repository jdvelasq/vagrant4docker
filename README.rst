Creación y uso de una máquina virtual como entorno de desarrollo usando Vagrant y Docker
*************************************************************************************************

Este repo contiene las instrucciones y demás archivos requeridos para la creación, configuración
y uso de una máquina virtual basada en Vagrant que permite la ejecución de contendores de Docker.


.. _contenido:

Contenido
-------------------------------------------------------------------------------------------------



Parte 1: Creación de la máquina virtual usando Vagrant
-------------------------------------------------------------------------------------------------

En esta práctica se realizará la configuración de un ambiente de
programación portable que garantice una ejecución idéntica en todos los
computadores independientemente del tipo de sistema operativo y su versión.
    
**Advertencia**. Este laboratorio debe ser realizado por fuera del campus
de la Universidad, ya que el proxy bloquea algunos de los sitios requeridos 
para la instalación de la máquina virtual.
  

Creación de la máquina virtual
-------------

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

  .. image:: ../assets/fig-01.jpg
    :width: 400
    :alt: Alternative text

Paso 5
  Habra el Terminal y vaya a la carpeta que contiene la copia de este repositorio. 

Paso 6
  Proceda con el encendido de la máquina de acuerdo a su sistema operativo. Las 
  instrucciones detalladas aparecen más adelante en este mismo documento. 

Solución de problemas
=================================================================================================

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








:ref:`contenido` vinculo











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
