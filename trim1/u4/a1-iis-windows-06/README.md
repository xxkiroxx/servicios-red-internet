# Práctica de Windows 2012 Server - Internet Information Server (IIS)
## Instalación de PHP, MySQL, PHPMyAdmin y FTP

- [1. Instalación de PHP](#1)
- [2. Instalación de MySQL](#2)
- [3. Creación Sitio Web phpmyadmin.miempresa.edu](#3)
- [4. Actualización Registro en el Servidor DNS](#4)
- [5. Instalación de PHPMyAdmin](#5)
- [6. Instalación de FTP](#6)
    - [6.1 Configuración Firewall](#7)
    - [6.2 Comprobamos desde navegador del cliente FTP](#8)
    - [6.3 Comprobamos desde un cliente FTP-Filezilla](#9)
- [7. Instalación y Configuración de Drupal](#10)
    - [7.1 Creación de Base de DAtos cms](#11)
    - [7.2 Instalación Drupal](#12)
    - [7.3 Configurando el diseño de Drupal](#13)
- [8. Instalación de WordPress](#14)


![](img/000.png)


## 1. Instalación de PHP<a name=1></a>
Tenemos que ir a la página http://windows.php.net y descargamos la version de `php-5.3.9-nts.msi`

![](img/001.png)

- Ya tenemos descargado el fichero de `php-5.3.9.msi` procesamos con la instalación.

![](img/002.png)

- Le damos siguiente.

![](img/003.png)

![](img/004.png)

- Seleccionamos IIS FastCGI para su correcto funcionamiento con el IIS.

![](img/005.png)

- Si nos sale el siguiente mensaje es que no tenemos una característica instalada en el IIS.

![](img/006.png)

- Tenemos que ir `Administrador del Servidor -> Agregar nuevos roles y tenemos que desplegar el Servidor IIS -> Desarrollo de Aplicación -> CGI`

![](img/007.png)

- Le damos siguiente y instalamos el `CGI`

![](img/008.png)

- Comienza la Instalación.

![](img/009.png)

- Ya tenemos instalado el `CGI` volvemos a iniciar la instalación de `php-5` y ya no sale el mensaje. Instalamos las siguientes opciones.

![](img/010.png)

- Proceso de instalación completada.

![](img/011.png)

- Si queremos comprobar que el servicio php esta funcionando correctamente tenemos que crear un fichero en la carpeta miempresa, llamado `index.php`

![](img/022.png)

- Vamos al navegador y escribimos `www.miempresa.edu` y no muestra una información de nuestro Equipo y la versión de PHP.

![](img/012.png)

## 2. Instalación de MySQL 5.7.20<a name=2></a>

Tenemos que ir a la página de MySQL y comenzamos a descargar el fichero.

![](img/013.png)

- Tenemos descargado el fichero de `MySQL` y comenzamos con la instalación.

![](img/014.png)

- Siguiente.

![](img/015.png)

- Seleccionamos solo `Server Only`

![](img/016.png)

- Execute para comprobar que esta correcta. Comprobamos que nos falta unas librerias de Microsoft Visual C++ 2013, las instalamos.

![](img/017.png)

- Ya podemos comenzar con la instalación.

![](img/018.png)

- Esperamos que se descargue `MySQL` y termina la instalación. Por lo tanto ya lo tenemos instalado.

![](img/019.png)

- Es necesario comprobar que nuestro sistemas Operativo tiene instalado el `Microsoft-Net Framework 4` Por lo tanto lo descargamos de su página oficial.

![](img/020.png)

- Se comprueba que está actualizado y instalado.

![](img/021.png)

- Se comprueba que la instalación está terminada y solo falta configurar el tipo de conexión.

![](img/023.png)

- Seleccionamos la que viene por defecto.

![](img/024.png)

- Dejamos la configuración por defecto.

![](img/025.png)

- Escribimos la contraseña de root.

![](img/026.png)

- Vamos a crear un usuario nuevo para la base de datos llamado `roberto`

![](img/027.png)

- Se comprueba que está agregado el nuevo usuario y le damos siguiente.

![](img/028.png)

- Dejamos la configuración por defecto.

![](img/029.png)

- Dejamos por defecto la configuración.

![](img/030.png)

- Siguiente.

![](img/031.png)

- Execute

![](img/032.png)

- Terminada la instalación y configuración de `MySQL`

![](img/033.png)
![](img/034.png)

## 3. Crear Sitio Web phpmyadmin.miempresa.edu<a name=3></a>

Primero tenemos que ir al IIS y creamos un nuevo sitio web llamado `phpmyadmin.miempresa.edu` y le decimos la ruta.

![](img/035.png)

- Comprobamos que se creo correctamente.

![](img/036.png)

## 4. Actualizar Registro en el Servidor DNS<a name=4></a>

Tenemos que ir al Servidor `DNS` y creamos un nuevo registro de alias llamado phpmyadmin.

![](img/038.png)

## 5. Instalación phpmyadmin<a name=5></a>

En la página oficial de phpmyadmin descargamos la versión `phpmyadmin4.0.10.20`

![](img/037.png)

- Se descarga un fichero comprimido lo que tenemos que realizar es pasar todo ese contenido a la carpeta que tenemos creada en mi `empresa/phpmyadmin` y copiamos todo el fichero de `phpmyadmin`.

![](img/039.png)

- Abrimos cualquier navegador y escribimos `phpmyadmin.miempresa.edu` y debe verse como la siguiente imagen.

![](img/040.png)

- Entramos con el usuario root y establecemos su contraseña.

![](img/041.png)

- Realizamos el mismo procedimiento desde un Equipo cliente `Windows 10` y escribimos en el navegador `phpmyadmin.miempresa.edu`

![](img/042.png)

- Comprobamos que funciona correctamente y se conecta con el usuario `roberto`

## 6. Instalación FTP-Server Filezilla<a name=6></a>

Descargamos de la página de Filezilla su aplicación para servidor y comenzamos con la instalación. Con este programa vamos a crear un servicio de `ftp` en nuestro windows server 2012

![](img/043.png)

- Ya tenemos descargado la aplicación de `filezilla-server` comenzamos con la instalación.

![](img/044.png)

- Aceptamos los términos.

![](img/045.png)

- Le damos siguiente.

![](img/046.png)

- Le damos siguiente.

![](img/047.png)

- Le damos siguiente.

![](img/048.png)

- Le damos instalar

![](img/049.png)

- Terminada la instalación.

![](img/050.png)

- Abrimos la aplicación y vamos a `Users -> creamos un usuario llamado ftpuser`

![](img/057.png)

- Le damos add y escribimos el usuario.

![](img/058.png)

- Escribimos `ftpuser`

Vamos a la pestaña llamada `shared folders` y establecemos la ruta que deseamos compartir para el usuario `ftpuser`

![](img/059.png)

- Establecemos los permisos necesarios para que el usuario `ftpuser` pueda trabajar sobre ese recursos compartido.

![](img/060.png)

### 6.1 Firewall<a name=7></a>

Tenemos que establecer una nueva regla en el corta fuegos del servidor para que puedan acceder al ftp mediante el puerto 21. `Panel de Control -> Firewall Avanzado -> nueva regla`

![](img/051.png)

- Se nos abre una nueva ventana y establecemos los puertos que deseamos abrir, en este caso `20, 21` y el protocolo `TCP`

![](img/052.png)

- Permitimos la conexión.

![](img/053.png)

- Seleccionamos para que se aplique en el `dominio, privado y público`

![](img/054.png)

- Establecemos un nombre a la regla `ftp`

![](img/055.png)

- Comprobamos que la regla está habilitada.

![](img/056.png)

### 6.2 Comprobamos desde navegador del cliente el FTP<a name=8></a>

Escribimos la dirección IP del servidor `ftp` y comprobamos que podemos acceder a los recursos compartidos, antes nos pide una autenticación del usuario `ftpuser`.

![](img/061.png)

- Realizamos el mismo procedimiento pero con nombre y comprobamos que funciona correctamente.

![](img/062.png)

- Podemos visualizar las carpetas que tiene acceso el usuario `ftpuser`

![](img/063.png)

### 6.3 Comprobamos desde un cliente FTP-Filezilla<a name=9></a>

Ejecutamos el programa cliente de filezilla en nuestro equipo cliente y solo tenemos que establecer la `dirección IP o subdominio`, escribimos el usuario con su contraseña y accedemos a su directorio.

![](img/064.png)

## 7. Instalación y Configuracion de Drupal 7.56<a name=10></a>

Lo primero que tenemos que realizar es ir a la página oficial de drupal y descargar la siguiente versión `drupal 7.56`(Seleccionamos esa versión porque es compatible con nuestro php).

![](img/065.png)

- Guardamos el fichero de drupal, que viene comprimido en un zip.

![](img/066.png)

- Descomprimimos el fichero drupal.

![](img/067.png)

- Nos conectamos al cliente filezilla y buscamos la ruta donde Descomprimimos el fichero de `drupal` y lo pasamos al servidor.

![](img/081.png)

### 7.1 Creación de Base de Datos cms<a name=11></a>

Primero tenemos que crear la base de datos `cms`

![](img/069.png)

- Creamos el usuario cms.

![](img/070.png)

- Se creo correctamente el usuario.

![](img/071.png)

- Establecemos privilegios al `usuario cms` para la base de datos `cms`

![](img/072.png)

### 7.2 Instalación de Drupal.<a name=12></a>

Solo tenemos que ir al navegador del cliente y escribir la siguiente dirección Web. `www.miempresa.com`

Seleccionamos por defecto la `standard`.

![](img/073.png)

- Tenemos que descargar de la página web que nos indicar `translation server` y descargamos nuestro idioma.

![](img/089.png)

Lo pasamos por filezilla al recurso compartido para `drupal`.

- La ruta sería `profiles -> standard -> translations`

![](img/078.png)

- Recargamos la página.

![](img/074.png)

- Seleccionamos el idioma.

![](img/075.png)

- Escribimos el nombre de la base de datos `cms` con el usuario `cms`

![](img/076.png)

- Esperamos que instale los módulos correspondientes.

![](img/077.png)

- Establecemos la información que nos pide.

![](img/079.png)

- Seguimos estableciendo la información que nos pide en el formulario y le damos guardar.

![](img/082.png)

- Ya tenemos configurado y instalado el `Drupal`.

![](img/080.png)

    Nota:

    Problema al instalar el Drupal, tenemos que ir al fichero de
    configuración `web.conf` y renombrarlo de la siguiente manera
    `web.conf.old`.

![](img/085.png)

- Ya tenemos configurado y instalado el drupal en nuestro servidor y por lo tanto al acceder con nuestro dominio `www.miempresa.com` nos tiene que visualizar el contenido de drupal.

![](img/083.png)

- Instalación del modulo para traducir el contenido.

![](img/084.png)

- Tenemos que ir a la pestaña apariencia y Seleccionamos instalar tema nuevo.

![](img/086.png)

- Buscamos el tema de `zen`.

![](img/087.png)

- Buscamos en la misma página y descargamos el tema de `zen`.

![](img/088.png)

- Solo nos falta añadir el tema y demos darle activar y establecer como preterminado.

![](img/090.png)

- Tenemos el tema añadido y establecido como preterminado.

![](img/091.png)

- Comprobamos y visualizamos que es diferente al que viene por defecto en `drupal`

![](img/092.png)

### 7.3 Configurando el diseño de Drupal<a name=13></a>

Vamos a crear un artículo en `drupal`. Para ello nos dirigimos al menú superior, pulsamos en contenido y clic en agregar contenido.

![](img/093.png)

Podemos ver el contenido creado.

![](img/094.png)

Comprobamos que podemos crear varios artículos a la vez.

![](img/095.png)

![](img/096.png)

Vamos agregar un menú, en que se muestran los enlaces importantes de nuestra página web.

![](img/097.png)

Añadimos un titulo y una pequeña descripción. Pulsamos en guardar y podemos gestionar nuestro menú.

![](img/098.png)

También se pueden crear bloques y situarlos en cualquier lugar de la página. Por ejemplo nosotros lo situaremos en el lateral izquierdo.

![](img/099.png)

Final de la página.

![](img/100.png)

## 8. Instalación de WordPress<a name=14></a>

Primero tenemos que agregar un sitio web llamado `blog.miempresa.com`

![](img/102.png)


Segundo tenemos que agregar un dns en el dominio de `empresa.com` llamado `blog`


![](img/101.png)

Creamos un usuario en el ftp llamado `WordPress` y le damos permisos total para modificar la carpeta de WordPress.

![](img/105.png)

Creamos una base de datos de WordPress y reutilizamos el usuario cms para que tenga privilegios en la base de datos `WordPress`.

![](img/109.png)
![](img/110.png)


Descargamos de la página web del WordPress desde el equipo cliente y lo pasamos por `ftp`

![](img/106.png)

Entramos al navegador del cliente y escribimos lo siguiente `blog.miempresa.com` y comenzamos con la instalación de WordPress. Solo tenemos que seguir el asistente.

![](img/104.png)

- Descargamos el WordPress

![](img/107.png)

- Seleccionamos el idioma español.

![](img/108.png)

- Requisitos para instalar el WordPress

![](img/111.png)

- Nombre de la base de datos y el usuario.

![](img/112.png)

- Comienzo de la instalación de la WordPress

![](img/113.png)

- Usuario para administrar el WordPress

![](img/114.png)

- Ya podemos acceder al WordPress

![](img/115.png)


Termina la instalación y comprobamos como tenemos instalado el `WordPress`.

![](img/116.png)
