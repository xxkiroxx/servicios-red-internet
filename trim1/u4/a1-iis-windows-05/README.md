# Práctica de Windows 2012 Server - Carpetas Privadas

## 1. Guiándote por los pasos detallados en el apartado de carpetas privadas del documento PDF de Carpetas Seguras y Privadas, vamos a crear un nuevo sitio web (empleados.miEmpresa.com) destinado a almacenar información privada de los empleados, con las siguientes características:

## 2. Crear una carpeta empleados (dentro de miempresa) y, dentro de esta, tres o cuatro subcarpetas personales con nombres de empleados y una, denominada común, a la que tendrán acceso todos los empleados, pero no otros usuarios sin identificar.

Primero creamos la carpeta `empleados en mi empresa.edu` con las siguientes subcarpetas de los siguientes usuarios.

![](img/001.png)

Comprobamos que se creo correctamente.

![](img/011.png)

## 3. Creamos los usuarios

Tenemos que ir a `usuarios y equipos de active directory` y creamos los siguientes usuarios.

Con el botón secundario del ratón le damos a `nuevo usuarios`.

![](img/004.png)

- Escribimos el nombre del usuario

![](img/002.png)

- Escribimos la contraseña del nuevo usuario.

![](img/003.png)

Captura de todos los usuarios creados.

![](img/005.png)

### 3.1 Creamos el grupo

Vamos a `usuarios y equipos de active directory`

![](img/022.png)

Creamos el grupo `comun`

![](img/023.png)

Agregamos los usuarios creados.

![](img/024.png)

## 4. Crearemos el nuevo sitio web, como subdominio de nuestro dominio principal, asociado a la carpeta genérica empleados.

Vamos al IIS y creamos un sitio web llamado empleados.miempresa.edu

![](img/006.png)

- Establecemos los valores que tenemos en la imagen.

![](img/007.png)

### 4.1 Configurar o actualizar DNS para empleados.miempresa.edu

Tenemos que entrar en el `Administrador de DNS` y establecemos un nuevo alias llamado `empleados`

![](img/008.png)

- Ya tenemos el nuevo registro del DNS y por lo tanto ya tenemos operativo el sitio Web para que funcione.

![](img/009.png)

- Realizamos un `nslookup` para comprobar su funcionamiento.

![](img/010.png)

### 4.2 Activar el Examen de directorios.

Vamos al sitio Web de empleados.miempresa.edu y vamos a `examen de directorios -> habilitar`

![](img/012.png)

- habilitar

![](img/013.png)

#### 4.2.1 Autenticación de los Directorios de los usuarios del Sitio Web empleados.miempresa.edu

Tenemos que ir a Autenticación y tenemos que deshabilitar el anónimo y habilitar el Autenticación básica.

![](img/014.png)

![](img/015.png)

Tenemos que realizar el mismo proceso con las demás carpetas de los usuarios.

## 5. Permisos en las Carpetas de los usuarios.

Vamos a realizar la prueba con una carpeta y luego debemos realizar el mismo trabajo para las demás carpetas.

Seleccionamos la carpeta de kevin y le damos propiedades.

![](img/016.png)

- Vamos a Seguridad y luego a opciones avanzadas.

![](img/017.png)

- Quitamos la herencia.

![](img/018.png)

- Quitamos todos la herencia.

![](img/019.png)

Agregamos el usuario para la carpeta y solo pueda entrar ese usuario.

![](img/020.png)

- Le damos permiso total para el usuario kevin.

![](img/021.png)

En la Carpeta publico agregamos el grupo nuevo llamado comun.

![](img/036.png)

### 5.1 Quitar Herencia a la carpeta empleados.

Vamos a la carpeta de empleados y le quitamos la herencia.

![](img/039.png)

- Quitamos la herencia.

![](img/040.png)

- Agregamos el grupo comun y Administradores

![](img/041.png)

- Agregamos el grupo IIS_USER

![](img/042.png)


## 6. Colocar un fichero index.html diferente en cada una de las carpetas creadas, con el objetivo de poder comprobar el acceso desde un navegador.

Creamos en cada carpeta de usuario un index.html

![](img/043.png)


## 7. Agregar función de Autenticación Básica a nuestro Servicio de IIS a través de la Administración del Servidor.

Agregamos la función de Autenticación Básica a nuestro servicio de IIS.

![](img/037.png)

- Vamos Autenticación y activamos Autenticación Básica.

![](img/038.png)



## 8. Comprobamos el acceso, tanto desde el servidor como desde el cliente W7, a las diferentes carpetas con distintos usuarios.

Realizamos comprobación con las siguientes conexiones de los usuarios.

Conectamos a empleados.miempresa.edu

![](img/026.png)

- Si queremos entrar en la página de Abraham debemos escribir su usuario y contraseña y accedemos.

![](img/027.png)

Como ya estamos logeado con el usuario Abraham y este está dentro del grupo comun, entonces podemos entrar a la carpeta publica sin ningún problema.


![](img/035.png)
