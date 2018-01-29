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

- Escribimos el nombre del ssitema de correo, por ejemplo escribimos `miempresa.com`

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

## 4. Instalación de cliente de correo en Ubuntu

Solo tenemos que abrir una terminal y escribir el siguiente comando para instalar la aplicación `evolution`

- `sudo apt install evolution`

![](img/020.png)

- Comienza la configuración de `Evolution` solo tenemos que darle siguiente.

![](img/021.png)


En el Equipo cliente debemos tener configurado en la tarjeta de red las `DNS` de nuestro servidor `ubuntu`.

![](img/023.png)

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

![](img/036.png)
![](img/037.png)
![](img/038.png)
![](img/039.png)
![](img/040.png)
