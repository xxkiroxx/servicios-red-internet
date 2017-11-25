# Práctica de Windows 2012 Server - Internet Information Server (IIS)
## Instalación de PHP, MySQL, PHPMyAdmin y FTP

## 1. Instalación de PHP
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

## 2. Instalación de MySQL 5.7.20

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

## 3. Crear Sitio Web phpmyadmin.miempresa.edu

Primero tenemos que ir al IIS y creamos un nuevo sitio web llamado `phpmyadmin.miempresa.edu` y le decimos la ruta.

![](img/035.png)

- Comprobamos que se creo correctamente.

![](img/036.png)

## 4. Actualizar Registro en el Servidor DNS

Tenemos que ir al Servidor `DNS` y creamos un nuevo registro de alias llamado phpmyadmin.

![](img/038.png)

## 5. Instalación phpmyadmin

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

## 6. Instalación FTP-Server Filezilla

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
