# Servicio FTP en Windows Server 2012

![](img/000.jpg)

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

- `Aislamiento de usuarios`: Es para que los usuarios no puedan subir mas arriba de su raíz establecida.

![](img/014.png)

- `Autenticación Básica`: Establecer que solo puedan conectarse los usuarios básicos de Windows o anónimos.

![](img/015.png)

- `Compatibilidad con el firewall:` Establecer reglas para el firewall

![](img/016.png)

- `Configuración SSL de FTP`: Configurar ftp para modo seguro y encriptado.

![](img/017.png)

- `Examen de Directorio`: Directorio raíz.

![](img/018.png)

- `Reglas de autorización`: Lo usuarios que pueden conectarse al `FTP`

![](img/019.png)

## 5. Conectarnos al FTP desde un navegador del servidor.

Tenemos que abrir el navegador y escribir el siguiente link `ftp://localhost`

![](img/020.png)

Comprobamos y vemos todos los ficheros de la unidad `C:\`.

![](img/021.png)

### 5.1 Accedemos desde un Equipo Cliente al ftp

Iniciamos o ejecutamos un navegador y escribimos lo siguiente. `ftp://ftp.miempresa.edu`.

![](img/022.png)

- Comprobamos que desde el cliente podemos conectarnos al `FTP`

![](img/023.png)

### 5.2 Instalación de WinSCP en el Equipo Cliente

Tenemos que entrar en la [página web de WinSCP](https://winscp.net/eng/docs/free_ftp_client_for_windows) y descargar el WinSCP cliente.

![](img/024.png)

- Comenzamos la instalación `WinSCP`.

![](img/025.png)

![](img/026.png)

![](img/027.png)

![](img/028.png)

![](img/029.png)

- Abrimos el `WinSCP` y establecemos el `usuario y la contraseña`.

![](img/030.png)

Comprobamos que iniciamos al `FTP` desde el Equipo Cliente.

![](img/031.png)

## 6. Configurar al directorio wwwroot de Inetpub para todos los usuarios.

Tenemos que agregar un sitio ftp nuevo.

![](img/006.png)

![](img/032.png)

Tenemos que configurar el enlace y SSL

Establecemos `permitir SSL` y establecemos un certificado SSL.

![](img/033.png)

- Establecemos que todos los usuarios se puedan conectar.

![](img/034.png)

- Importante tenemos que cambiar el `puerto ftp` porque entra en conflicto con el otro sitio de `FTP`.

![](img/035.png)

![](img/036.png)

### 6.1 En el Equipo Cliente nos conectamos al Servidor FTP mediante WinSCP.

Abrimos el programa de WinSCP y comprobamos si podemos iniciar sesión mediante `cifrado explícito`

![](img/037.png)

Comprobamos que podemos acceder al FTP.

![](img/038.png)

## 7. Crear un Sitio Nuevo FTP para usuarios anónimos.

Tenemos que ir al `IIS y crear un sitio FTP nuevo`.

![](img/006.png)

![](img/039.png)

Le damos siguiente.

![](img/040.png)

Importante cambiar el puerto en este caso `2122` para no crear conflicto con los otros sitios FTP

Configuramos la autenticación y autorización.`Solo para anónimos`

![](img/041.png)

Permiso solo de `Leer`.

![](img/042.png)

### 7.1 Conectarnos desde el Programa WinSCP desde el Cliente.

Abrimos el WinSCP.

![](img/043.png)

Accedemos al recurso de `FTP`.

![](img/044.png)

Comprobamos si el usuario anónimos puede cambiar permisos.

![](img/045.png)

Comprobamos que no puede cambiar nada, solo tiene permiso de lectura.

## 8. Comprobar que funciona el DNS con todos los FTP creados mediante WinSCP desde el Equipo Cliente.

Tenemos que abrir el WinSCP en el Equipo Cliente.

- Conexión con el Sitio `FTP` para un usuario especifico `Administrador`.

![](img/030.png)

![](img/031.png)


- Conexión con el Sitio `FTP` para todos los usuarios

![](img/048.png)

![](img/047.png)

- Conexión con el Sitio `FTP` para anónimos

![](img/043.png)

![](img/044.png)
