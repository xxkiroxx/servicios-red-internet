# DNS en Windows Server 2012

- [Instalación y Configuración DNS](#1)

- [Creación de Zona Búsqueda Directa](#2)

- [Creación de Zona Búsqueda Inversa](#3)

- [Configuración de Reenviadores](#4)

- [Comprobar el funcionamiento del DNS caché](#5)

- [Configuración DNS Maestro](#6)

- [Crear una Subzona demoninada servicios](#7)

- [Comprobar desde consola del cliente que resuelvan nslookup type](#8)

- [Realizar operaciones con nslookup fuera de la intranet](#9)



![img](img/000.jpg)

## Realizar la instalación y configuración de un servidor DNS en una máquina con Windows Server 2012. Se piden las siguientes acciones de configuración y prueba del funcionamiento del servicio:<a name="1"></a>

Tenemos que abrir la ventana de `Administrador del servidor -> Administrar -> Agregar Roles`.


![img](img/001.png)

- Le damos siguiente para seleccionar el servicio `DNS`.

![img](img/002.png)
![img](img/003.png)
![img](img/004.png)

- Seleccionamos el Servidor `DNS`.

- En nuestro caso ya tenemos instalado el DNS porque hemos instalado en la práctica anterior un `Directorio activo` y que por defecto instala el servicio de `DNS`.

![img](img/005.png)


Comprobamos que tenemos el servicio instalado en el siguiente ruta `Administrador del servidor -> Herramientas -> DNS`


![img](img/006.png)

- Se nos abre una ventana nueva de `Administrador de DNS`, comprobamos en la `zonas de búsqueda directa`


![img](img/007.png)




## Creación de una nueva Zona Búsqueda Directa <a name="2"></a>

Tenemos que entrar en `Administador del servidor -> Herramientas -> DNS`

- Con el botón secundario del ratón seleccionamos `Zona nueva`.

![img](img/009.png)
![img](img/010.png)
![img](img/011.png)

- Seleccionamos Zona Principal y le damos siguientes.

![img](img/012.png)
![img](img/013.png)

- Escribimos un nombre nuevo para la zona.

![img](img/014.png)
![img](img/015.png)
![img](img/016.png)

- Por lo tanto ya tenemos configurado una nueva zona Directa.

## Crear una zona de búsqueda inversa para tu subred.<a name="3"></a>

En la carpeta de `Zonas de Búsqueda inversa` con el botón secundario del ratón creamos una nueva zona inversa.


![img](img/017.png)

- Seleccionamos `Zona Principal`

![img](img/018.png)
![img](img/019.png)
![img](img/020.png)
![img](img/021.png)
![img](img/022.png)
![img](img/023.png)

- Ya tenemos configurado la nueva `Zona de Búsqueda inversa`.


## Configurar reenviadores de DNS con fry o puerta de enlace actual y DNS público (p.e.: 195.235.113.3 / 80.58.61.250 / 8.8.8.8).<a name="4"></a>

Seleccionamos nuestro servidor `serverob2 -> Propiedades -> reenviadores`

![img](img/025.png)

- Seleccionamos `reenviadores`

![img](img/026.png)

- Le damos a editar para añadir nuevos `reenviadores`

![img](img/027.png)

- Ya tenemos configurado los nuevos reenviadores para que se convierta en `Servidor Caché de DNS`

## Configurar el servidor para ser servidor DNS Caché (en la configuración estática de red).

![img](img/008.png)

### Configurar cliente para que su servidor DNS sea el servidor W2012. Comprobar el funcionamiento como caché DNS de ambas máquinas al acceder a sitios de Internet.<a name="5"></a>

Configuramos la tarjeta de red con la IP del DNS del Servidor Windows Server 2012.

- Realizamos dos pruebas para ver si funciona correctamente el DNS. Desde el Equipo cliente utilizamos el comando `nslookup`.


![img](img/029.png)

![img](img/028.png)

## Configuraremos el servidor como DNS Maestro, además de Caché.<a name="6"></a>

La configuración de un Servidor DNS Maestro solo con tener registros en el propio servidor de DNS, como por ejemplo, `cname, mx, a`. Ya hemos creado una zona directa y vamos a crear un alias para el servidor, para impresora y un email.

## En la zona de búsqueda directa añadir los siguientes registros:

![img](img/024.png)

![img](img/030.png)

### Comprobación con el comando `nslookup`

![img](img/046.png)

### Un alias para tu servidor denominado server.

![img](img/031.png)

### Comprobación con el comando `nslookup`

![img](img/043.png)

![img](img/047.png)

### Una impresora con IP fija denominada printer (no hace falta alias).

![img](img/024.png)

![img](img/033.png)


### Comprobación con el comando `nslookup`

![img](img/044.png)

### Un servidor de correo (ficticio) denominado correo, asociado a una dirección en tu servidor.

Solo tenemos que seleccionar el nuevo intercambio de correo MX.

![img](img/032.png)

![img](img/034.png)

### Comprobación con el comando `nslookup`

![img](img/045.png)

## Registros en la Zona de búsqueda directa

Registros de los hosts con el nombre.

![img](img/048.png)

## Registros en la Zona de búsqueda inversa

Registros de los hosts con la IP

![img](img/049.png)


## Crear una subzona denominada servicios (dominio nuevo)<a name="7"></a>

Vamos a crear una nueva zona en la zona directa. Solo debemos seguir los mismos pasos.

![img](img/009.png)
![img](img/010.png)
![img](img/011.png)
![img](img/050.png)
![img](img/051.png)
![img](img/052.png)

### Creamos la Subzona de servicios

Con el botón secundario del ratón en la nuevazona y le damos `dominio nuevo`.

![img](img/062.png)

- Escribimos el nombre de `servicios`

![img](img/063.png)


### Agregar a ésta un servidor ftp (asociado a la misma IP del servidor)

![img](img/053.png)
![img](img/054.png)

#### Comprobación con el comando `nslookup`

![img](img/059.png)

### Una impresora nueva (con una IP fija)

![img](img/053.png)
![img](img/055.png)

#### Comprobación con el comando `nslookup`

![img](img/060.png)

### El equipo del administrador del sistema (también con IP fija).

![img](img/053.png)
![img](img/056.png)

#### Comprobación con el comando `nslookup`

![img](img/061.png)

### Validar un cliente en el dominio y comprobar que el nombre de su equipo aparece en la zona de búsqueda del servidor como un nuevo registro A.


![img](img/053.png)
![img](img/058.png)


### Registros en el nuevo zona de búsqueda directa, llamada `servicios`

![img](img/057.png)


### Comprobar desde la consola del cliente que se resuelven correctamente los nombres dados de alta en el servidor (aunque en algunos casos, si se trata de direcciones ficticias, no se obtenga respuesta).<a name="8"></a>

```console

C:\Windows\system32>nslookup printer2.servicios.skynet.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  printer2.servicios.skynet.edu
Address:  172.18.22.6


C:\Windows\system32>nslookup server
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  serverob2.skynet.edu
Address:  172.18.22.1
Aliases:  server.skynet.edu


C:\Windows\system32>nslookup -type=mx mail
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

mail.skynet.edu MX preference = 10, mail exchanger = mailserver.skynet.edu
mailserver.skynet.edu   internet address = 172.18.22.5

C:\Windows\system32>nslookup -type=cname server
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

server.skynet.edu       canonical name = serverob2.skynet.edu

C:\Windows\system32>nslookup -type=a printer2.servicios.skynet.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  printer2.servicios.skynet.edu
Address:  172.18.22.6


C:\Windows\system32>nslookup administrador.servicios.skynet.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  administrador.servicios.skynet.edu
Address:  172.18.22.7


C:\Windows\system32>nslookup cliente1.servicios.skynet.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  cliente1.servicios.skynet.edu
Address:  172.18.22.10


C:\Windows\system32>nslookup ftp.servicios.skynet.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  ftp.servicios.skynet.edu
Address:  172.18.22.1


C:\Windows\system32>nslookup mailserver
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  mailserver.skynet.edu
Address:  172.18.22.5


C:\Windows\system32>nslookup printer
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  printer.skynet.edu
Address:  172.18.22.4


C:\Windows\system32>


```

### Realizar desde el cliente, algunas operaciones con nslookup fuera de nuestra intranet.<a name="9"></a>


```console

C:\Windows\system32>nslookup www.google.es
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Respuesta no autoritativa:
Nombre:  www.google.es
Addresses:  2a00:1450:4003:806::2003
          216.58.211.195


C:\Windows\system32>nslookup www.facebook.es
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Respuesta no autoritativa:
Nombre:  star-mini.c10r.facebook.com
Addresses:  2a03:2880:f104:83:face:b00c:0:25de
          31.13.83.36
Aliases:  www.facebook.es
          www.facebook.com


C:\Windows\system32>nslookup www.elotrolado.net
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Respuesta no autoritativa:
Nombre:  elotrolado.net
Address:  195.78.228.226
Aliases:  www.elotrolado.net


```
