# U6-A2 | Instalación y Configuración de un Servidor de Correo en GNU/Linux

![](img/000.png)

## 1. Instalar el servicio SMTP en Ubuntu, utilizando el servidor Postfix

Tenemos que abrir una terminal en `ubuntu` y solo tenemos que escribir el siguiente comando.

- `sudo apt install postfix`

![](img/001-1.png)

- En el proceso de instalación nos saldra un aviso indicandonos que tipo de configuración del servidor de correo se ajusta mejor para nuestra necesidad.

En este caso vamos a marcar el correo `SMTP`.

![](img/001-2.png)

- Seleccionamos el tipo de configuración de correo, `sitio de Internet`.

![](img/002.png)

- Escribimos el nombre del sistema de correo, por ejemplo escribimos `miempresa.com`

![](img/003.png)

Comprobamos que el servicio `SMTP` está escuchando.

El comando `netstat` nos indica los puertos o servicios que está a la escucha el servidor.

- Solo tenemos que utilizar el siguiente comando `netstat -utap`

![](img/004-1.png)

Si queremos ver que el servicio esta funcionando y no tiene ningún error.

- `sudo systemctl status postfix`

![](img/004-2.png)

- `netstat -ntap`

![](img/005.png)


## 2. Realiza una prueba de envio de mensaje entre dos usuarios de UNIX mediante telnet

Escribimos el comando `telnet` para comprobar que podemos conectarnos al puerto `25` de nuestro servidor.

![](img/006.png)

Creamos dos usuarios llamados `eric` y `stan` y vamos al fichero `/etc/passwd` para ver si están creado correctamente.

![](img/007.png)

Con el usuario `eric` realizamos un envío de mail al usuario `stan`.

![](img/008.png)

![](img/009.png)

- Le damos quit para salir de la conexión.

![](img/010.png)

- Establecemos conexión con el usuario `stan`

![](img/011.png)

- Vamos a la siguiente ruta para comprobar el mail `/var/spool/mail`

![](img/012.png)

- Vemos que tenemos un fichero llamado `stan` vamos a realizar un `cat` para comprobar su contenido.

![](img/013.png)

En el fichero de `stan` vemos que tenemos el correo enviado de `eric`


## 3. Crear una Zona Maestra en bind9

Tenemos que ir a la siguiente ruta `/etc/bind/named.conf.local` y modificamos el fichero para crear una zona maestra nueva.

![](img/014.png)

Solo tenemos que escribir lo que tenemos en el marco rojo de la foto.

![](img/015.png)

- Tenemos que abrir el fichero `db.miempresa` para crear los registros nuevos.
    - `smtp -> 172.18.21.81`
    - `pop -> 172.18.21.81`

![](img/016.png)

Realizamos una comprobación para ver si funciona la resolución de nombre.

- `ping smtp.miempresa.com`

![](img/017.png)

- `ping pop.miempresa.com`

![](img/018.png)

## 4. Instalación de cliente de correo en Windows

Solo tenemos que instalar un gestor de correo en `Windows` en este caso será el `OperaMail`.


En el Equipo cliente debemos tener configurado en la tarjeta de red las `DNS` de nuestro servidor `ubuntu`.

![](img/023.png)

Abrimos el `OperaMail` y creamos una cuenta de un usuario nuevo de correo.

- Escribimos el mail del usuario `eric`

![](img/024.png)

- Configuramos con el correo normal `pop`

![](img/025.png)

- Configuramos el servidor entrada `pop.miempresa.com`
- Configuramos el servidor saliente `smtp.miempresa.com`

![](img/026.png)

- Comprobamos que tenemos la cuenta mail de `eric` configurado.

![](img/027.png)

Vamos a enviar un correo desde el usuario `eric` a `stan`

![](img/028.png)

Tenemos que ir al servidor y en la siguiente ruta `/var/spool/mail`

![](img/029.png)

Vemos el correo que recibio `stan` del usuario `eric`.

![](img/030.png)

Ahora vamos a realizar el mismo procedimiento de envió de correo pero en este caso desde `stan` a `eric`.

![](img/031.png)

 Vamos al servidor y comprobamos `/var/spool/mail` que tenemos el correo de `stan` a `eric`.

![](img/032.png)

## 5. Instalación del servicio IMAP

Tenemos que abrir una terminal y escribimos el siguiente comando para instalar el servicio de correo `IMAP`.

![](img/033.png)

- Comprobamos que el servicio está funcionando correctamente.

![](img/034.png)

- Realizamos una comprobación de puerto a la escucha.
    - `netstat -utap | grep imap`

![](img/035.png)

## 6. Instalación de Squirrelmail

Comenzamos con la instalación de `Squirrelmail`.

- Escribimos el siguiente comando para instalar el `Sequirrelmail`

- `sudo apt install squirrelmail`

![](img/036.png)

- Ruta de ficheros de configuración de `squirrelmail` en `/etc/squirrelmail`

![](img/037.png)

- Ruta del directorio de la aplicación `squirrelmail` en `/usr/share/squirrelmail`

![](img/038.png)

## 7. Creación de un Virtual Host en Apache2

Tenemos que ir a la ruta de `sites-available` creamo un fichero nuevo de virtual host con el nombre de `squirrelmail.conf`.

![](img/039-1.png)

Con el siguiente comando `a2ensite squirrelmail.conf` creamos un enlace simbólico en `sites-enabled`.

Realizamos también un reinicio del servicio de `apache2` y comprobamos su estado.

![](img/040.png)

## 8. Conectar a Squirrelmail desde el Servidor Ubuntu.

Solo tenemos que abrir un navegador y escribir `localhost/squirrelmail` y se nos muestra una página de autenticación.

![](img/041.png)

## 9. Conectar a Squirrelmail desde Cliente Windows.

Solo tenemos que abrir un navegador y escribir `miempresa.com/squirrelmail` y escribimos el nombre del usuario `eric` para acceder al correo.

![](img/042.png)

- Comprobamos la bandeja de entrada de `eric` y vemos que recibio un correo de `stan`

![](img/043.png)

Vamos a enviar un correo a `stan` por lo tanto tenemos que ir a `compose`.

![](img/044.png)

- Escribimos el mail de `stan` y escribimos un texto de prueba y le damos a `send`

![](img/045.png)

- Vemos en la bandeja de salida que se envió un correo de `eric` a `stan`

![](img/046.png)

Entramos en la cuenta de `stan`

![](img/047.png)

Comprobamos en la bandeja de entrada de `stan` que tenemos varios mensajes de `eric`.

![](img/048.png)

Vamos a conectar al correo de `eric` desde la cuenta de `stan`, solo tenemos que darle reply.

![](img/049.png)

Escribimos el correo de `eric` y el texto que le vamos a enviar.

![](img/050.png)

Vamos a la cuenta de `eric` para comprobar si nos llego el correo de `stan`.

![](img/051.png)

- Comprobamos que en la bandeja de entrada de `eric` tenemos un correo de `stan`

![](img/052.png)

- Abrimos dicho correo y vemos el resultado.

![](img/053.png)

## 10. Comprobamos que en el servidor están los contenedores de los correos de stan y eric

Tenemos que ir a la siguiente ruta en el servidor `/var/mail`

Vemos que tenemos dos contenedores de los correos de `eric` y `stan`.

![](img/054.png)

- Comprobamos si el correo de `eric` tiene correo de `stan`.

![](img/055.png)

- Comprobamos si el correo de `stan` tiene correo de `stan`.

![](img/056.png)

## 11. Instalación de POP3

Solo tenemos que abrir una terminal y escribir el siguiente comando.

- `sudo apt install dovecot-pop3d`

![](img/057.png)

Comprobamos los puertos de `POP3`

![](img/058.png)

![](img/059.png)

Comprobamos que el servicio de `dovecot` con el `POP` y `IMAP` está activado y funcionando.

![](img/059-1.png)

### 11.1 Configurar en Dovecot del servidor para que funcione el POP

Tenemos que ir a la siguiente ruta `/etc/dovecot/conf.d` para escribir dentro del fichero de configuración `10-auth.conf`.

![](img/066.png)

- Modificamos la linea de `ssl` y establecemos `no`
  - `ssl = no`

- Modificamos la línea de `disable_plaintext_auth` y establecemos `no`
  - `disable_plaintext_auth = no`

![](img/067.png)

- Ya tenemos configurado y solo tenemos que reiniciar el servicio de `dovecot.service`

![](img/068.png)

## 12. Configurar cuenta de correo en Windows con OperaMail.

Abrimos el programa de correo `OperaMail` y seguimos el asistente para crear una cuenta de correo para `eric`

![](img/060.png)

- Escribimos el correo y su contraseña. Importante marcar el `correo normal POP`


![](img/061.png)

- Escribimos en el servidor de entrada `pop.miempresa.com`
- Escribimos en el servidor de salida `smtp.miempresa.com`

![](img/062.png)

- Realizamos el mismo procedimiento con la cuenta de correo para `stan`

![](img/063.png)

- Configuramos el nombre de usuario y su contraseña.

![](img/064.png)

- Escribimos en el servidor de entrada `pop.miempresa.com`
- Escribimos en el servidor de salida `smtp.miempresa.com`

![](img/065.png)

Vamos a realizar una prueba de envio de correo desde la cuenta de `eric` a `stan`.

![](img/069.png)

- Comprobamos que el correo llega a la bandeja de entrada de `stan`.

![](img/070.png)

Vamos a realizar un correo desde la cuenta de `stan` a `eric`

![](img/071.png)

- Comprobamos que llega correctamente el correo de `stan` en `eric`

![](img/072.png)

Vamos al Servidor de correo de `Ubuntu` y comprobamos en `/var/mail` que tenemos todavía los contenedores de `stan`

![](img/073.png)

- Comprobamos también el contenedor de correo de `eric`

![](img/074.png)

Por defecto en los ficheros de configuración de `dovecot` no elimina los contenedores de correo de los usuarios `eric` y `stan`.
