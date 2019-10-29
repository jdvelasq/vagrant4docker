.. _parte-5:

Parte 5: Ejecución de una imagen
=================================================================================================

Las imágenes pueden ser ejecutadas directamente desd el Terminal o desde VS code.


Ejecución de una imagen desde el Terminal usando docker-compose
-------------------------------------------------------------------------------------------------

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
-------------------------------------------------------------------------------------------------

Una vez haya conectado VS code de forma remota a la máquina virtual y haya instalado el 
complemento de Docker, usted podrá visualizar las imágenes descargadas la máquina virtual.


Para ejecutar una imagen:


1. Haga click en el ícono de Docker en la barra vertical de la parte derecha de VS code.

2. Haga click en el menu `IMAGES` y luego en la imagen correspondiente para ver los tags 
   disponibles.

3. Haga click en el boton derecho sobre el tag y seleccione `Run interactive`.  

  .. image:: assets/fig-11.jpg
    :width: 400
    :alt: fig-11