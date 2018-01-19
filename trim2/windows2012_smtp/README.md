# Windows 2012 Server SMTP

![](img/000.png)

## 1. Agregar Roles de SMTP

Tenemos que ir a `administrador del servidor -> agregar nuevos roles`

![](img/001.png)

![](img/002.png)

![](img/003.png)

![](img/004.png)

- Seleccionamos características. Marcamos `SMTP`

![](img/005.png)

![](img/006.png)

![](img/007.png)

Vamos a `herramientas -> Administrador de Internet Information Services (IIS) 6.0`

![](img/008.png)

- Seleccionamos el `SMTP Virtual Server` y con el botón secundario del ratón le damos a `propiedades`

![](img/009.png)


### 1.1 Configuramos la `Dirección IP`

![](img/010.png)

### 1.2 Limitar el número de conexiones a 50

![](img/013.png)

### 1.3 Habilitar el registro en formato W3C, diario y en una carpeta determinada.

Vamos a la pestaña general, habilitamos en el registro, le damos propiedades.

![](img/015.png)


### 1.4 Configurar envío de mensajes dentro de nuestra red local: Aceptar la conexión al servidor y la retransmisión de mensajes a todos los equipos menos los que aparecen en la lista (incluir una IP cualquiera en la lista para impedir su acceso y retransmisión)

En caso que queremos denegar una IP, solo tenemos que agregar dicha dirección IP

![](img/014.png)

### 1.5 Establecer autenticación anónima

![](img/011.png)

- Seleccionamos autenticación.

![](img/012.png)

### 1.6 Echar un vistazo al resto de opciones de configuración del servidor. Aplicar cambios y reiniciar servicio.

- Comprobamos la pestaña de mensajes. En este apartado es para limitar el tamaño de los mensajes.

![](img/016.png)

- Entrega de los mensajes

![](img/017.png)

- Enrutamiento con LDAP

![](img/018.png)

- Seguridad

![](img/019.png)

### 1.7 Comprobar la existencia del dominio AD predeterminado. Crea un dominio de tipo alias para disponer de cuentas en otro dominio.

En dominios le damos nuevo.

![](img/021.png)

![](img/022.png)

- Escribimos el nombre del dominio.

![](img/023.png)

![](img/024.png)

### 1.8 Comprueba carpetas de correo creados en C:\Inetpub\mailroot.

Comprobamos que se crearón correctamente las carpetas de correo.

![](img/020.png)

## 2. En el cliente Windows 7:

### 2.1 Comprobar acceso al nuevo nombre DNS creado en el servidor.

Vamos a utilizar el dominio de `skynet.edu`


### 2.2 Configurar el cliente de correo Live mail agregando dos cuentas de correo cualesquiera (usuarios AD -dominio- y no AD). Se deberá especificar: usuario / buzón, contraseña,  servidor SMTP.

Vamos a la página de opera y descargamos el `opera live`

![](img/025.png)

Instalamos el programa y configuramos el gestor de correo electrónico.

![](img/026.png)

Configuramos el correo, en este caso como es anónimo podemos inventarnos el email.

![](img/027.png)

Configuramos el usuario. Inventado y contraseña.

![](img/028.png)

Configuramos el SMTP con el nombre del dominio `skynet.edu`

![](img/029.png)

Comprobamos que enviamos el correo electrónico en una cuentra ficticia.

![](img/030.png)

Comprobamos en los ficheros del servidor.

![](img/033.png)

Abrimos el siguiente fichero y comprobamos que intenta enviar el correo.

![](img/031.png)

Comprobamos que funciona con una cuenta real mía.

![](img/032.png)

En el corrreo electrónico mio y compruebo que está correctamente recibido en el spam.

![](img/034.png)

- Comprobamos en el cliente Opera los correos enviados.

![](img/035.png)


## 3. Nueva configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Establecer autenticación básica de Windows. Probar diferentes configuraciones de dominio predeterminado, cifrado TLS, etc.

Primero tenemos que ir al IIS 6.0 y establecer en comunicación segura `TLS` y luego vamos a autenticación.

![](img/040.png)

Seleccionamos autenticación básica y marcamos el TLS

![](img/041.png)


## 4. En el cliente Windows:

### 4.1 Configurar las cuentas según los parámetros especificados en el servidor. Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío y carpetas mailroot. En este caso sólo tendrán acceso al servidor SMTP cuentas del dominio y correspondientes a usuarios de AD.

Configuramos una cuenta de correo del directorio activo `kevin, oscar`

![](img/038.png)

![](img/039.png)

Escribimos un correo electrónico.

![](img/044.png)

Muestra un mensaje para aprobar el `TLS`

![](img/042.png)

Nos fijamos en la carpeta de `mailroot`

![](img/043.png)

![](img/045.png)

Enviamos el correo al correo electrónico mío.

![](img/046.png)
