Creación y uso de una máquina virtual como entorno de desarrollo
=================================================================================================

Este repo contiene las instrucciones y demás archivos requeridos para la creación, configuración
y uso de una máquina virtual basada en Vagrant que permite la ejecución de contendores de Docker.

* [Parte 1. Creación de la máquina virtual ](parte-1-creacion-vm.rst)

* :ref:`parte-2`.

* :ref:`parte-3`.

* :ref:`parte-4`.

* :ref:`parte-5`.


Resumen
=================================================================================================

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
========================================

* `What is Vagrant? <https://www.vagrantup.com/intro/index.html>`_

* `Getting Started <https://www.vagrantup.com/intro/getting-started/index.html>`_.

* `Puppet Apply Provisiner <https://www.vagrantup.com/docs/provisioning/puppet_apply.html>`_.

* `Docker tutorial <https://docs.docker.com/get-started/>`_.
