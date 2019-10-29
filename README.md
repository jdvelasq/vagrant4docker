Creación y uso de una máquina virtual como entorno de desarrollo
=================================================================================================

Este repo contiene las instrucciones y demás archivos requeridos para la creación, configuración
y uso de una máquina virtual basada en Vagrant que permite la ejecución de contendores de Docker.

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
