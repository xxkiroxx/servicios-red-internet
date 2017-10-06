# DHCP UBUNTU

- [Instalación del servicio DHCP en Ubuntu](#id1)

- [Configuración del servicio DHCP:](#id2)

    - [Creación de un ámbito nuevo asociado al dominio con el intervalo de direcciones IP que consideres conveniente.](#id3)

    - [Configurar puerta de enlace y servidores DNS a suministrar a los clientes.](#id4)

    - [Configurar resto de opciones necesarias.](#id5)

    - [Establecer una reserva de dirección asociada a un equipo específico (MAC).](#id6)

    - [Resetear el servicio de DHCP](#id7)

- [Comprobar funcionamiento DHCP configurando adecuadamente la máquina cliente y anotando parámetros recibidos](#id8)

- [Tener en cuenta que el servidor no debe estar abierto a la red (configurar adaptador en red interna) para no provocar conflictos de direcciones.](#id9)

![imagen](img/dhcp.png)


## Instalación del servicio DHCP en Ubuntu <a name="id1"></a>

Primero tenemos que instalar el servicio de DHCP, por lo tanto debemos escribir el siguiente comando que muestra en la imagen.

![imagen](img/001.png)

## Configuración del servicio DHCP<a name="id2"></a>

Para configurar los ficheros de configuración de DHCP, tenemos que ir a la siguiente ruta.

    cd /etc/dhcp/dhcpd.conf

![imagen](img/002.png)

Para editar el fichero debemos utilizar un comando llamado nano o gedit.

> Importante
    Realizar una copia de seguridad del fichero dhcpd.conf.

![imagen](img/003.png)


### Creación de un ámbito nuevo asociado al dominio con el intervalo de direcciones IP que consideres conveniente. <a name="id3"></a>

Tenemos que editar el fichero dhcpd.conf.

![imagen](img/004.png)

En mi caso utilizamos una red de clase B con una mascara de /24


### Configurar puerta de enlace y servidores DNS a suministrar a los clientes.<a name="id4"></a>

En el mismo fichero añadimos nuevos parámetros para configurar los DNS y puerta de enlace.

![imagen](img/005.png)

### Configurar resto de opciones necesarias.<a name="id5"></a>

En el mismo fichero debemos crear unos paramétros nuevos para las nuevas opciones.

![imagen](img/009.png)

### Establecer una reserva de dirección asociada a un equipo específico (MAC). <a name="id6"></a>

En el mismo ficheros escribimos las siguientes líneas y parámetros.

![imagen](img/010.png)

Fichero final de configuración del dhcpd.conf

![imagen](img/013.png)

### Resetear el servicio de DHCP <a name="id7"></a>

Solo tenemos que escribir el comando que tenemos en la imagen, para recargar todos los ficheros de configuración del dhcp creado.

![imagen](img/006.png)

Para ver si esta funcionando el servicio escribimos el siguiente comando.

![imagen](img/007.png)

Si en algún momento el servicio te da algún error, debemos ir al fichero log, para ver que problema tiene.

    cat /var/log/syslog

### Comprobar funcionamiento DHCP configurando adecuadamente la máquina cliente y anotando parámetros recibidos. <a name="id8"></a>

Se comprueba en un equipo cliente Ubuntu que obtiene un dirección IP.

![imagen](img/012.png)

El comando ifconfig enp0s3 down y up es para activar y desactivar la tarjeta de red.

Como reserva la IP es la 172.18.22.11.

![imagen](img/014.png)

Comprobamos con el entorno gráfico.

![imagen](img/018.png)

Realizamos con un Equipo de Windows para ver si le da una dirección IP

![imagen](img/016.png)

Como se comprueba no da la dirección IP 172.18.22.11, porque está reservada para el Equipo Cliente de Ubuntu.


### Tener en cuenta que el servidor no debe estar abierto a la red (configurar adaptador en red interna) para no provocar conflictos de direcciones. <a name="id9"></a>

Todas las configuraciones de los Equipos cliente y el servidor tienen las tarjeta de red en modo interno con su mismo nombre.

![imagen](img/015.png)
