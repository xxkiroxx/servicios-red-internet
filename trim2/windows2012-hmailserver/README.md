
![](img/000.png)

# ¿Que es HMailServer?

HMailServer es un servidor de correo gratuito y libre, para Microsoft Windows desarrollado en Suecia.

Es compatible con los protocolos habituales (IMAP, SMTP, POP3) e incorpora una biblioteca COM que puede usarse para su integración con otro software, o para realizar tareas complejas de manera automatizada a través de scripts. Admite también dominios virtuales, listas de distribución, antivirus, anti-spam, alias, dominios distribuidos, seguridad integrada con el Directorio Activo de Windows, Backup y bastantes cosas más.

## 1. Descargar HMailServer

Vamos a la página Web de [HMailServer](https://www.hmailserver.com/download) y descargamos la última versión.

![](img/001.png)

## 2. Instalación de HMailServer.

Comenzamos con la instalación de `hmailserver`.

![](img/002.png)

- siguiente

![](img/003.png)

- Aceptamos los términos.

![](img/004.png)

- La ruta donde queremos instalar el `hMailServer`.

![](img/005.png)

- Seleccionamos las características.

![](img/006.png)

- Creación de la Base de datos.

![](img/007.png)

![](img/008.png)

- Escribimos la contraseña para el administrador.

![](img/009.png)

- Le damos a instalar.

![](img/010.png)

- Te pedirá que necesita el `NET Framework 2.0`

![](img/011.png)

- Al comenzar con la instalación nos dice que no puede instalar el `Net Framework 3.5`.

![](img/014.png)

- Tenemos que ir `agregar roles nuevos -> Instalar Net Framework 3.5`

![](img/012.png)

- Le damos siguiente para comenzar con la instalación.

![](img/013.png)

Comprobamos que termina la instalación.

![](img/015.png)

- Se nos abre una nueva ventana que nos permite conectar al `HMailServer`.

![](img/016.png)

## 3. Crear dos dominios llamados `srd.edu` y `asir.edu`

Entramos a la aplicación o servicio de `HMailServer` y agregamos el siguiente dominio.

![](img/017.png)

- `srd.edu`

![](img/018.png)

- `asir.edu`

![](img/019.png)

- Comprobamos que están creado los dos dominios independientes al Directorio Activo.

![](img/020.png)

## 4. Ejecuta los diagnósticos para ambos dominios y soluciona el error de backup asignando una carpeta para tal fin. Establece copia de seguridad de los mensajes.

Vamos a `Utilities -> Diagnostics` seleccionamos un dominio.

![](img/021.png)

- Comprobamos que da errores de backup porque no tenemos asignada ninguna carpeta.

![](img/022.png)

- Comprobamos los cambios realizados.

![](img/023.png)

- Comprobamos que ya no nos muestra el error de backup.

- Pero muestra un mensaje de `MX` es problema de DNS.


## 5. Crea dos cuentas para dos usuarios ficticios en cada uno de los dos dominios. Investiga y configura las cuentas con diferentes opciones (cuota de disco, auto-reply, forwarding, signature, etc.)

Vamos a las pestañas de dominio de `asir.edu` y `srd.edu`

- Vamos a Accounts y le damos a añadir un usuario nuevo.

![](img/024.png)

- El usuario que vamos a crear se llamará `suso`

![](img/025.png)

- Configuramos `Auto-Reply` para contestar automáticamente un correo.

![](img/026.png)

- Creamos un usuario `kevin`

![](img/027.png)

- Configuramos `Auto-Reply` para contestar automáticamente un correo.

![](img/028.png)

- Configuramos el `Forwarding` para que le llegue al correo de `Abraham`

![](img/029.png)

- Configuramos el `Signature`

![](img/030.png)

- Comprobamos que tenemos creado los usuarios `suso y kevin`

![](img/031.png)

- Vamos al dominio de `srd.edu` y creamos el usuario `abraham`

![](img/032.png)

- Configuramos el `Auto-reply`

![](img/033.png)

- Creamos un usuario llamado `noelia`

![](img/034.png)

- Configuramos el `Auto-reply`

![](img/035.png)

- Usuarios creados en el dominio `srd.edu` los usuarios `abraham y noelia`

![](img/036.png)

## 6. Configura el servicio DNS para crear las entradas srd.edu y asir.edu que apunten a la dirección ip del servidor windows 2012.

Vamos al `DNS` y vamos a crear dos zonas maestras nuevas.

- `asir.edu`
- `srd.edu`

![](img/037.png)

- Creamos un registro de `MX` en el dominio de `asir.edu`

![](img/038.png)

- Creamos un registro de `MX` en el dominio de `srd.edu`

![](img/039.png)

Vamos a `HMailServer` y vamos a realizar un diagnostico para comprobar que funciona correctamente los `MX`.


- Realizamos el test con el dominio `srd.edu`

![](img/040.png)

- Realizamos el test con el dominio `asir.edu`


## 7. Realiza todas las opciones de configuración que consideres necesarias y/o convenientes. Consulta para ello los tutoriales cuyos enlaces se proporcionan (opciones de protocolos SMTP, POP e IMAP, rangos de IP, bloqueo de correo entrante, nombre de host, reenvío dominios remotos, blacklists, opciones de logging, etc.)


Primero configuramos los servicios de `POP3`, `SMTP` y `IMAP`.

![](img/041.png)


- `SMTP`: Configuramos las conexiones permitidas, `0` es ilimitado las conexiones.

![](img/042.png)

- `Local host`

![](img/049.png)

- `POP3`

![](img/043.png)

- `IMAP`

![](img/044.png)

Configuramos el `Anti-Spam` en el `hMailServer`.

![](img/045.png)

Configuramos los `rangos de IP`.

![](img/046.png)


Configuramos el `Auto-Ban`

![](img/047.png)


Configuramos las opciones de `logging`.

![](img/048.png)


## 8.Configura en el cliente W7 un cliente de correo como thunderbird o Live Mail (en los ordenadores clientes) para acceder al servidor de correo instalado en Windows 2012.

Vamos a configurar un correo electrónico con el usuario `suso`.

![](img/049.png)

- Vamos al Equipo cliente Win7 y abrimos el `Opera Mail` configuramos un correo nuevo para el usuario `suso`

![](img/050.png)

- Escribimos las configuraciones necesarias para el usuario `suso`

![](img/051.png)

- El usuario debe ser `suso@asir.edu`

![](img/052.png)

- Escribimos el nombre del servidor donde nosotros tenemos un registro tipo `MX` en mi caso en `asir.edu`


![](img/053.png)

- Ya tenemos configurado un usuario con su correo.

- Con el `Usuario Kevin` enviamos un correo electrónico al usuario `suso`


![](img/054.png)


- Comprobamos que llega el correo electrónico a la bandeja de entrada de `suso`



![](img/055.png)


## 9.Realiza prueba de envío y recepción de correos entre los diferentes usuarios, comprobando, además de envío y recepción correctas, el efecto de las opciones configuradas en las cuentas.


Ya tenemos configurado los usuarios `kevin@asir.edu`, `suso@asir.edu`, `noelia@srd.edu` y `abraham@srd.edu` en gestor de cuentas de correo electrónico llamado `Opera Mail`


- Comprobamos con el usuario de `kevin`, todo el correo que le llega debe redirigir toda su bandeja al correo de `abraham`.

![](img/056.png)

- Comprobamos que no tenemos ninguna correo electrónico en ninguna cuenta.

![](img/058.png)


Envio un correo electrónico desde la cuenta `noelia` a la cuenta de `kevin`.

![](img/057.png)

- Comprobamos que reenvia todo el correo electrónico a la cuenta de `abraham`

![](img/059.png)


- Con el usuario `noelia` configuramos el auto-reply.

![](img/060.png)

- Enviamos un correo electrónico con el usuario `kevin` a `noelia`

![](img/061.png)

- Comprobamos que llega bien el correo electrónico al usuario `noelia`

![](img/062.png)

- Como tenemos que el usuario `kevin` todo su correo debe ir redirigido a `abraham` vamos a la cuenta de abraham y llega un `Auto-Replay` de `noelia`.

![](img/063.png)


## 10. Crea una lista de distribución empleados asociada al dominio y añade a los dos usuarios de miempresa.com a ella.


Primero tenemos que ir a `hMailServer` y vamos al dominio de `asir.edu` y vamos a la carpeta de `Distibution lists` vamos a crear un grupo llamado `asir` para los dos correos electrónico `suso y kevin`.

![](img/064.png)

- Comprobamos que tenemos añadido los usuarios `kevin y suso` al grupo `asir`

![](img/065.png)

- Realizamos el mismo procedimiento con el dominio `srd.edu` y creamos un grupo llamado `srd` con los usuarios `noelia y abraham`.

![](img/066.png)

- Desde una cuenta de usuario `suso` enviamos un correo al grupo `srd@srd.edu`

![](img/067.png)

- Comprobamos que llego correctamente el correo en la bandeja de `abraham`

![](img/068.png)

- Comprobamos que llego correctamente el correo en la bandeja de `suso`

![](img/069.png)

- Enviamos un correo al grupo `asir@asir.edu`

![](img/070.png)

- Comprobamos que llegan bien los correos electrónicos.

![](img/071.png)
