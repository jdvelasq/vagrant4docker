Instalación y uso de las extensiones de VScode
=================================================================================================

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
    :width: 400
    :alt: fig-02  


Paso 5
  Haga click en  `SSH TARGETS` y luego en el símbolo de `+`. 
  
  .. image:: assets/fig-03.jpg
    :width: 400
    :alt: fig-03


Paso 6
  En el comando de conexión digite `ssh vagrant4docker`. 
  
  .. image:: assets/fig-04.jpg
    :width: 400
    :alt: fig-04  


Paso 7
  El sistema le solicitará que indique cual archivo de configuración desea modificar. Use el suyo por defecto.
      
  .. image:: assets/fig-05.jpg
    :width: 400
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
