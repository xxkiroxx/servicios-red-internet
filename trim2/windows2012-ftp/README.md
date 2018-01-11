# Servicio FTP en Windows Server 2012

![](img/000.png)

## 1. Agregar roles de FTP en Windows Server 2012

Tenemos que ir al administrador del servidor y le damos agregar roles.

![](img/001.png)

Le damos siguiente.

![](img/002.png)

Activamos la pestaña de Servidor `FTP`.

![](img/003.png)

Le damos a instalar y comenzará la instalación del servicio de `FTP`.

![](img/004.png)

## 2. Configurar FTP

Tenemos que ir a `administrador del servidor -> herramientas -> Administrador de Internet Information Services (IIS)`.

![](img/005.png)

En Sitios web le damos `agregar sitio FTP`

![](img/006.png)

- Se abre una nueva ventana y debemos configurar los siguientes paramétros.

![](img/007.png)

Le damos siguiente.

Tenemos que configurar en la siguiente ventana la `dirección IP, si quieres que tenga SSL y habilitar un virtual host`.

![](img/008.png)

- Configuramos en el siguiente paso, la autenticación, en este caso marcamos.
    - Anónima: `Desactivado`
    - Básica: `Habilitado`

- Permitir acceso a usuarios especificados:
    - `Administrador`
    - Permiso: `Leer y Escribir`

![](img/009.png)

Ya tenemos configurado el FTP.


## 3. Configurar en el DNS el alias ftp.miempresa.edu

Tenemos que ir `administrador del servidor -> DNS`

![](img/011.png)

Creamos el nuevo alias llamado `ftp`

![](img/012.png)

Configuración final

![](img/013.png)

## 4. Comprobamos los ficheros de configuración del ftp

Los siguientes ficheros son para configurar el servidor ftp.

![](img/010.png)
