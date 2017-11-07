## Creación de 2 sitios Web llamado `www.terminator.edu` y `t800.terminator.edu` este es un subdominio del dominio principal de `terminator.edu`.

Lo primero que tenemos que realizar es meter en el VirtualBox del servidor Windows server 2012 un `disco duro nuevo de 1GB`.

![](img/001.png)

Iniciamos el Windows Server 2012 y le damos formato al nuevo disco duro para que sea reconocible por el Sistema Operativo.

![](img/002.png)

Creamos las siguientes carpetas en `E:\`.

![](img/012.png)

### Comenzamos para crear dos nuevos sitios Web. Tenemos que ir `Administrador -> Internet Information Services (IIS)`

![](img/003.png)

Estamos dentro de la ventana de IIS, solo tenemos que situarnos en Sitios y con el botón secundario del ratón `agregar sitio Web nuevo`.

![](img/004.png)

Creamos los nuevos dos Sitios Web.

- Sitio Web 1 Dominio Principal http://www.terminator.edu

![](img/005.png)

- Sitio Web 2 Subdominio del Dominio Principal http://t800.terminator.edu

![](img/006.png)

- Resultado Final de los dos Dominios creados.

![](img/009.png)

### Tenemos que Crear una Zona Directa nueva llamada terminator.edu

Lo primero tenemos que crear una zona directa seguimos el asistente, agregamos nuevos alias, por ejemplo `www` y tambien algún registor `A` como se muestra en la imagen.

![](img/010.png)

Creamos una zona de subdominio llamada `t800`

![](img/011.png)

### Realizamos Comprobación desde el Equipo para ver si podemos acceder a los Sitios Web.

- Sitio Web 1 `www.terminator.edu`

![](img/007.png)

- Sitio Web 1 `www.terminator.edu/informes`

![](img/014.png)

- Sitio Web 2 `t800.terminator.edu`

![](img/008.png)

- Sitio Web 2 pero subcarpeta `t800.terminator.edu/t1`

![](img/013.png)

Realizamos comprobación con el comando `nslookup`

```console
C:\Windows\system32>nslookup www.terminator.edu
Servidor:  t800.terminator.edu
Address:  172.18.22.1

Nombre:  serverob2.terminator.edu
Address:  172.18.22.1
Aliases:  www.terminator.edu


C:\Windows\system32>nslookup t800.terminator.edu
Servidor:  serverob2.skynet.edu
Address:  172.18.22.1

Nombre:  t800.terminator.edu
Address:  172.18.22.1


C:\Windows\system32>
```
