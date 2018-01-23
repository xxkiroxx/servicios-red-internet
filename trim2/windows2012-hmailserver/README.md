
![](img/000.png)

# ¿Que es HMailServer?

HMailServer es un servidor de correo gratuito y libre, para Microsoft Windows desarrollado en Suecia.

Es compatible con los protocolos habituales (IMAP, SMTP, POP3) e incorpora una biblioteca COM que puede usarse para su integración con otro software, o para realizar tareas complejas de manera automatizada a través de scripts. Admite también dominios virtuales, listas de distribución, antivirus, anti-spam, alias, dominios distribuidos, seguridad integrada con el Directorio Activo de Windows, Backup y bastantes cosas más.

## 1. Descargar HMailServer

Vamos a la página Web de [HMailServer](https://www.hmailserver.com/download) y descargamos la última versión.

![](img/001.png)

## 2. Instalación de HMailServer.

![](img/002.png)
![](img/003.png)
![](img/004.png)
![](img/005.png)
![](img/006.png)
![](img/007.png)
![](img/008.png)
![](img/009.png)
![](img/010.png)
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


![](img/024.png)
![](img/025.png)
![](img/026.png)
![](img/027.png)
![](img/028.png)
![](img/029.png)
![](img/030.png)
![](img/031.png)
![](img/032.png)
![](img/033.png)
![](img/034.png)
![](img/035.png)
![](img/036.png)

## 6. Configura el servicio DNS para crear las entradas mail.srd.edu y mail.asir.edu que apunten a la dirección ip del servidor windows 2012.

Vamos al `DNS` y vamos a crear dos zonas maestras nuevas.

![](img/037.png)

![](img/038.png)

![](img/039.png)
