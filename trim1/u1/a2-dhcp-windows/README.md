# Windows Server 2012-DHCP

- [Instalación DHCP en Windows Server 2012](#id1)

- [Configuración del servicio DHCP](#id2)

    - [Creación de un ámbito nuevo asociado al dominio con el intervalo de direcciones IP que consideres convenientes.](#id3)

    - [Agregar exclusiones de direcciones](#id4)

    - [Configurar puerta de enlace y servidores DNS a suministrar a los clientes.](#id5)

    - [Configurar resto de opciones necesarias](#id6)

    - [Establecer una reserva de dirección asociada a un equipo específico (MAC)](#id7)

    - [Configurar algunas opciones de ámbito además de las habituales](#id8)

    - [Configurar también algunas opciones de servidor (aplicables a todos los ámbitos)](#id9)

- [Comprobar funcionamiento DHCP configurando adecuadamente la máquina cliente y anotando parámetros recibidos](#id10)


- [Tener en cuenta que el servidor no debe estar abierto a la red (configurar adaptador en red interna) para no provocar conflictos de direcciones](#id11)

- [Crear un nuevo ámbito con los parámetros (rangos, exclusiones, reservas, opciones de ámbito) que te parezcan oportunas y que sea compatible con el anterior](#id12)

- [Comprobar el funcionamiento del nuevo ámbito desde el cliente](#id13)

- [Crear un superámbito DHCP que incluya a los dos ámbitos anteriores](#id14)

- [Desactivar el superámbito y comprobar que DHCP deja de prestar servicio en ambos ámbitos](#id15)

![imagen](img/win.png)

## Instalación DHCP en Windows Server 2012<a name="id1"></a>
 Tenemos que ir administrador, luego vamos añadir roles nuevos.

 ![imagen](img/001.png)

 Seguimos el asistente de Windows. Llegaremos al apartado que tenemos que activar el servicio DHCP

  ![imagen](img/002.png)

  Seguimos con la instalación.

  ![imagen](img/003.png)


  Seleccionamos DHCP Server nos pedirá agregar los componentes necesarios.
  Seguimos el asistente de Windows hasta llegar a la configuración DHCP.

   ![imagen](img/004.png)

  Completar la instalación, seguimos el asistente de Windows.

  ![imagen](img/005.png)

  ![imagen](img/006.png)

  ![imagen](img/007.png)

## Configuración del servicio DHCP<a name="id2"></a>

Tenemos que ir al administrador del servidor, seleccionamos la pestaña herramienta y elegimos DHCP.

 ![imagen](img/008.png)

 Se abre la ventana nueva para crear los ámbitos.

  ![imagen](img/009.png)

### Creación de un ámbito nuevo asociado al dominio con el intervalo de direcciones IP que consideres convenientes.<a name="id3"></a>

Tenemos que desplegar el IPv4 para crear un nuevo ámbito.

![imagen](img/010.png)

Seguimos el asistente de Windows.

![imagen](img/011.png)

![imagen](img/012.png)

![imagen](img/013.png)

Alquiler de una dirección IP al equipo cliente.

![imagen](img/015.png)

![imagen](img/018.png)

![imagen](img/019.png)

Se termina la creación de un nuevo ámbito.

![imagen](img/020.png)

### Agregar exclusiones de direcciones.<a name="id4"></a>

Para agregar exclusiones de direcciones lo podemos realizar desde que estamos creando el ámbito de DHCP.

![imagen](img/014.png)

Podemos crear nuevas exclusiones en el Servidor.

![imagen](img/021.png)


### Configurar puerta de enlace y servidores DNS a suministrar a los clientes.<a name="id5"></a>

Configuración de la Puerta de enlace

![imagen](img/016.png)

Configuración de los DNS

![imagen](img/017.png)


### Configurar resto de opciones necesarias.<a name="id6"></a>

Tenemos que ir al ámbito creado en el DHCP-dpto-tecnico y buscamos la opciones del ámbito.

Se abre una nueva ventana y dentro podemos configurar diferentes opciones, en este caso sera la de recursos compartidos en una red.

![imagen](img/027.png)

### Establecer una reserva de dirección asociada a un equipo específico (MAC). <a name="id7"></a>

En el servicio de DHCP tenemos que ir a la carpeta reserva y con el botón derecho del ratón creamos una nueva.

![imagen](img/024.png)

### Configurar algunas opciones de ámbito además de las habituales.<a name="id8"></a>

En la carpeta de ámbito tenemos varias opciones para configurar, en este caso yo configuro una ubicación para recursos.

![imagen](img/027.png)

### Configurar también algunas opciones de servidor (aplicables a todos los ámbitos).<a name="id9"></a>

![imagen](img/049.jpg)

Se abre una nueva ventana y podemos configurar las siguientes opciones.

![imagen](img/048.jpg)

## Comprobar funcionamiento DHCP configurando adecuadamente la máquina cliente y anotando parámetros recibidos.<a name="id10"></a>

Ejecutamos un cliente Windows 10 y comprobamos que el servidor DHCP este funcionando.

![imagen](img/025.png)

## Tener en cuenta que el servidor no debe estar abierto a la red (configurar adaptador en red interna) para no provocar conflictos de direcciones.<a name="id11"></a>

Es importante que tengamos en el VirtualBox configurado la tarjeta de red en modo interno.

![imagen](img/034.png)

## Crear un nuevo ámbito con los parámetros (rangos, exclusiones, reservas, opciones de ámbito) que te parezcan oportunas y que sea compatible con el anterior.<a name="id12"></a>

Importante antes de crear un ámbito nuevo, tenemos que agregar una nueva tarjeta de red al Servidor 2012 desde el VirtualBox y en modo red interna y le cambiamos el nombre de la red interna.

![imagen](img/052.jpg)

Ejecutamos el Windows Server 2012 y cambiamos los nombres de la tarjeta de red por si nos equivocamos.

![imagen](img/053.jpg)

Creamos un nuevo ámbito. Seguimos el mismo procedimiento que el ámbito anterior.

![imagen](img/035.jpg)

En este caso voy a utilizar una red de clase c.

![imagen](img/036.jpg)

El rango de dirección IP es el siguiente:

![imagen](img/038.jpg)

Realizamos una reserva para la siguiente IP

![imagen](img/037.jpg)

## Comprobar el funcionamiento del nuevo ámbito desde el cliente.<a name="id13"></a>

Vamos al Equipo Cliente y le agregamos desde el VirtualBox una nueva tarjeta red, pero en modo red interna y con un nombre diferente.

Iniciamos el Windows 10, realizamos el siguiente comando.

    ipconfig /release
    ipconfig /renew

Como muestra en la siguiente imagen, a la tarjeta de red llamada tecnico, nos da un dirección IP del DHCP-Dpto Técnico y la tarjeta de red llamada comercial, nos da una dirección IP del DHCP-dpto-comercial.

![imagen](img/051.jpg)


## Crear un superámbito DHCP que incluya a los dos ámbitos anteriores.<a name="id14"></a>

Se crea un superámbito, solo tenemos que ir al servidor y con el botón secundario del ratón buscar la opción que dice superámbito. Seguimos el asistente de Windows.

![imagen](img/043.jpg)

Le damos siguiente

![imagen](img/044.jpg)

seleccionamos los ámbitos

![imagen](img/045.jpg)

El proceso de la creación de los super ámbito termina.

![imagen](img/046.jpg)

## Desactivar el superámbito y comprobar que DHCP deja de prestar servicio en ambos ámbitos.<a name="id15"></a>

Al desactivar el superámbito el servicio de DHCP no funciona en ninguno.

![imagen](img/047.jpg)

Comprobación en el Equipo Cliente que no funciona el DHCP, no tiene ninguna dirección IP

![imagen](img/050.jpg)
