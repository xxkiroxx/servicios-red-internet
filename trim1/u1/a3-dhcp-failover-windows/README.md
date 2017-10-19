# DHCP Failover Windows Server 2012

- [Agregar un segundo Servidor](#1)

- [DHCP del Servidor Principal](#2)

    - [Configuración conmutación por error ( DHCP Failover)](#3)

    - [DHCP secundario](#4)

    - [Equipo Cliente](#5)

- [Captura con el Servidor DHCP Principal suministrando IP al Equipo Cliente](#6)

- [Captura con el Servidor DHCP Secundario suministrando IP al Equipo Cliente](#7)


![imagen](img/000.png)

    Trabajo Realizado por:

        [Noelia Hernández Domínguez]()
        [Kevin Hernández García]()
        [Roberto Hernández Sanabria](https://github.com/xxkiroxx/servicios-red-internet/blob/master/trim1/u1/a3-dhcp-failover-windows/README.md)



## Agregar un segundo Servidor<a name="1"></a>
Tenemos que ir a la ventana administrador del Servidor.

![imagen](img/003.png)

![imagen](img/002.png)

Solo tenemos que darle buscar ahora, te salen los servidores disponibles, seleccionamos el servidor y le damos a la flecha para pasarlo para el cuadro de la derecha. Los servidores ya se conocen entre ellos, dentro de su directorio activo.


## DHCP del Servidor Principal<a name="2"></a>

Tenemos creado ya dos ámbitos de DHCP en el servidor principal.

![imagen](img/001.png)

- DHCP del servidor Secundario

![imagen](img/008.png)


### Configuración conmutación por error ( DHCP Failover)  <a name="3"></a>

Con el botón secundario del ratón en el servidor principal y seleccionamos configurar conmutación por error.

![imagen](img/005.png)

Se nos abre una nueva venta en la que seleccionamos los ámbitos.

![imagen](img/006.png)

Tenemos que buscar el servidor secundario para que pueda pasar toda la información de la configuración de los ámbitos.

![imagen](img/009.png)

Podemos escribir la IP o ir agregar servidor.

![imagen](img/007.png)

Seleccionamos el servidor secundario.

Le damos aceptar y se nos abre una nueva ventana para crear una nueva relación.

El modo es equilibrio de carga, le damos siguiente.

![imagen](img/010.png)

![imagen](img/011.png)

![imagen](img/012.png)

También podemos configurarlo en el modo de `espera activa, espera`. Si configuramos está opción el servidor secundario se quedá a la espera de que falle el servidor principal de DHCP.

![imagen](img/021.png)


El modo de `espera activa, activa`. Si configuramos está opción el servidor secundario está siempre activo, falle o no el servidor principal.

![imagen](img/022.png)

### Eliminación de Conmutaciónpor error

Solo tenemos que seleccionar el protocolo IPv4, le damos propiedades, seleccionamos la pestaña conmutación por error y eliminamos las existente.

![imagen](img/023.png)


### DHCP secundario<a name="4"></a>

Solo tenemos que darle actualizar y se tiene que actualizar todas las configuraciones de los ámbitos del DHCP principal.

![imagen](img/013.png)

Después de actualizar.

![imagen](img/014.png)


## Equipo Cliente<a name="5"></a>

Realizamos un `ipconfig /release` y `ipconfig /renew`

![imagen](img/015.png)

Realizamos un `ipconfig /all`

![imagen](img/017.png)

Se comprueba y el Servidor DHCP principal no está dando la dirección IP.

Para simular un fallo del servidor DHCP Principal, desactivamos el DHCP principal.

Realizamos de nuevo un Realizamos un `ipconfig /release` y `ipconfig /renew`

![imagen](img/016.png)

El servidor secundario DHCP está dando dirección IP al Equipo cliente.



## Captura con el Servidor DHCP Principal suministrando IP al Equipo Cliente<a name="6"></a>

![imagen](img/020.png)

## Captura con el Servidor DHCP Secundario suministrando IP al Equipo Cliente<a name="7"></a>

![imagen](img/019.png)
