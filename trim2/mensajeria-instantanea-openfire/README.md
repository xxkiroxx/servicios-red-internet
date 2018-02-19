# U7-A1 | Instalación y Configuración de un Servidor de Mensajería Instantánea Openfire en Windows Server 2012

![](img/000.png)


## 1. Comprobar en nuestro servidor tenemos instalado los servicio IIS, PHP, MySQL y phpMyAdmin.

Comprobamos que tenemos instalado el servicio de `IIS`.

![](img/001.png)

Comprobamos que tenemos instalado el servicio de `MySQL`.

![](img/002.png)

Comprobamos que tenemos instalado el `phpMyAdmin`.

![](img/003.png)

## 2. Descargar Openfire

Vamos a la página web oficial de la aplicación de Mensajería `Openfire`.

![](img/004.png)

Seleccionamos `Openfire_4_2_2_bundledJRE_x64.exe` lo descargamos y al comenzar con la instalación seleccionamos el idioma `Español`.

![](img/005.png)

Seguimos el asistente de instalación de `Openfire`.

![](img/006.png)

Marcamos la casilla de iniciar el servicio de `Openfire`.

![](img/007.png)

## 3. Crear una Base de Datos para Openfire

Abrimos un navegador y entramos a la aplicación de `phpMyAdmin` y creamos la base de datos.

![](img/008.png)

- Creamos un usuario para la base de datos de `Openfire`.

![](img/009.png)

Le damos permiso al usuario para que tenga acceso completo a la base de datos de `Openfire`.

![](img/010.png)

## 4. Configuración de Openfire

Tenemos que abrir en un navegador y poner `localhost:9090` el `9090` es el puerto para abrir la aplicación de `Openfire`.

![](img/011.png)

Seleccionamos el idioma `Español`

![](img/012.png)

- Lo dejamos por defecto y le damos siguiente.

![](img/013.png)

- Conexión Estándar y continuar.

![](img/014.png)

- Seleccionamos la base de datos `MySQL` y escribimos el nombre de la base de datos `openfire`.

![](img/015.png)

- La configuración del perfil lo dejamos por defecto.

![](img/016.png)

- Cuenta de administrador.

![](img/017.png)

Escribimos en el navegador del servidor `localhost:9090`

![](img/018.png)

- Escribimos el nombre del `usuario` y `contraseña`.

![](img/019.png)

Comprobamos que podemos acceder a la configuración de `openfire`.

![](img/021.png)

- Comprobamos que podemos acceder desde el navegador del equipo cliente con el el dominio `miempresa.com:8080`

## 5. Instalación de la aplicación Spark

Vamos a la página y descargamos el `Spark`

![](img/022.png)

Descargamos el `spark_2_8_3`

![](img/023.png)

Le damos a instalar y siguiente.

![](img/024.png)

Seguimos el asistente de la aplicación `Spark`

![](img/025.png)

Ya termino la instalación.

![](img/026.png)

- Se abre la aplicación con `Spark`

![](img/027.png)

Vamos al equipo cliente y instalamos el `Spark`



## 6. Creación de Usuario para Openfire

Creación de usuario de `eric`

![](img/028.png)

Creamos el usuario `stan`

![](img/029.png)

Listado de usuarios creados.

![](img/030.png)

Tenemos que abrir la aplicación de `Spark` y marcas las siguientes casillas.

![](img/031.png)

Iniciamos la aplicación `Spark` y nos logeamos con el usuario `Stan`

![](img/032.png)

Comprobamos que podemos acceder a la cuenta de `stan`

![](img/033.png)

Nos logeamos con el usuario `Eric`

![](img/034.png)

Vemos que entramos con la cuenta de `eric`

![](img/035.png)

Vamos a agregar el contacto de eric.

![](img/036.png)

![](img/037.png)

Lo metemos en el grupo de amigos.

![](img/038.png)

Envió un mensaje a `eric`

![](img/039.png)

Vemos que el mensaje llega correctamente.

![](img/040.png)

Vamos a crear una conferencia nueva.

![](img/041.png)

Le damos a crear conferencia

![](img/042.png)

Establecemos el nombre a la sala.

![](img/043.png)

Para entrar en la sala solo tenemos que buscarla en conferencia y nos unimos.

![](img/044.png)

Los dos usuarios escriben algo en la sala.

![](img/045.png)

Se puede enviar fotos.

![](img/046.png)

El usuario acepta la foto y la puede visualizar

![](img/047.png)


![](img/048.png)

## 7. Instalación de SparkWeb

Vamos a la página web y descargamos la aplicación de `SparkWeb`

![](img/049.png)

Descomprimimos la carpeta de `SparkWeb` en la unidad `c:`

![](img/050.png)

Comprobamos su contenido.

![](img/051.png)

Vamos al `IIS` y creamos una virtual host nuevo.

![](img/052.png)

Vamos al Servicio de `DNS` y lo llamamos `sparkweb.miempresa.com`

![](img/053.png)

Añadimos al documento predeterminado `SparkWeb.html`

![](img/054.png)

Instalamos el adobe flash player.

![](img/055.png)

Intentamos acceder a la página, pero no funciona el botón login.

![](img/056.png)
