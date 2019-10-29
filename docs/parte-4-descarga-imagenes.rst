.. _parte-4:

Parte 4: Descarga de las imágenes desde Docker Hub.
=================================================================================================

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
  
    **Python 3**
    
      .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/python:3.7
              
    **Apache Pig**
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/pig:0.18.0

    **Apache Mahout**
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/mahout:0.14.0

    **Apache Hive**
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/hive:2.3.5
    
    
    **Apache Spark**
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/spark:2.4.3
    
    
    **Open Refine**
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/openrefine:3.2

    **Apache Superset**
    
    
    .. code-block::
    
        vagrant@ubuntu-bionic:/vagrant$ docker pull jdvelasq/superset:0.34.0


  3. Use las imágenes y continue su trabajo. O finalice su trabajo apagando la máquina virtual. 
     La ejecución de las imágenes puede realizarse desde VS code o desde el Terminal, tal como 
     se indica en las siguientes partes de la documentación.

