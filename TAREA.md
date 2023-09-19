#1.Descarga la imagen 'ubuntu y comprueba que está en tu equipo

    Con **docker search** buscamos la imagen
    La descargamos con **docker pull ubuntu**
    Por ultimo comprobamos con **docker images**

#2.Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

   Creamos el contenedor: **docker run -it ubuntu bash**: Con este comando ya esta arrancado.
   Obtenemos el nombre: **docker ps** :
   
   3dea535761cc   ubuntu    "bash"    44 seconds ago   Up 43 seconds    compassionate_williamson

#3.Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?

    Creamos el contenedor con el comando --name le damos un nombre:
   
    **docker run -it --name ubu1 ubuntu bash**
   
    Con el anterior comando ya accedemos a el, en el caso de que estuviese parado:
   
    **docker start ubu1**
    **docker exec -it ubu1 bash**

#4.Comprueba que ip tiene y si puedes hacer un ping a google.com

    Instalamos y actualizamos las herramientas necesarias para utilizar ifconfig y ping:
    
    **apt update**
    **apt upgrade**
    **apt install net-tools**
   **apt install iptools-ping**

    **ifconfig** : ip: 172.17.0.3
    **ping google.com** : si que se puede

#5.Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?

    Creamos el contenedor: **docker run -it --name ubu2 ubuntu bash**
    Utilizamos los comandos anteriores para instalar las herramientas necesarias:
    **ifconfig**     ip:127.17.0.4
    **ping 127.17.0.3** : si que podemos hacer ping entre los contenedores


#6.Sal del terminal, ¿que ocurrió con el contenedor?

    Al cerrar la terminal (exit) . El contenedor se para. Para volver a acceder a el tenemos que usar un docker start y un    docker exec -it (nombre) bash.

#7.¿Cuanta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?

    Con el comando docker stats podemos ver el uso de recursos de nuestros contenedores. En el caso de ubu1 ocupo 114MB.


#8.¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.

    Utilizando el mismo comando vemos que ubu1 utiliza 51.5 Mib.