# Instalación de Windows Server 2012 y Ubuntu 16.04
<hr>

![imagen](img/001.png)
## 1. Instalación e configuración de Windows Server 2012
<hr>

Primero tenemos que ejecutar el VirtualBox y crear una máquina virtual para Windows Server 2012.

## 1.1.1 Configuración de la Máquina Virtual Windows Server 2012

Creamos la máquina virtual con las siguientes características.

![imagen](img/002.png)

### 1.1.2 Instalación Windows Server 2012
Ejecutamos la iso desde la máquina virtual. Seguimos los pasos que nos indica el asistente.

![imagen](img/003.png)

Seleccionamos GUI (Es la parte con entorno gráfico)

![imagen](img/004.png)

Configuramos el formato del disco duro para la instalación.

![imagen](img/005.png)

### 1.1.2 Nombre Equipo

En el servidor vamos a cambiar el nombre del equipo.

![imagen](img/006.png)

### 1.1.3 Configuración de la Tarjeta de Red
En las propiedades de la tarjeta de red, configuramos las siguientes IP.

![imagen](img/007.png)

### 1.1.4 Instalación Directorio Activo
Buscamos el administrador del servidor y agregamos nuevos roles.

![imagen](img/008.png)

Seguimos el asistente y seleccionamos el servicios de dominio Active Directory.

![imagen](img/009.png)

Le damos agregar y esperamos que termine el proceso de instalación.

![imagen](img/010.png)

Termina el proceso de instalación y por último necesitamos crear un bosque de dominio nuevo, tenemos que seleccionar promover y escribimos nuestro dominio.

![imagen](img/011.png)

En el proceso de instalación posiblemente salgo un mensaje de advertencia que no tenemos un DNS, por lo tanto instalará el servicio de DNS.

### 1.1.5 Comprobación del Equipo Cliente unido al dominio
Tenemos que ir a herramientas administrativas, usuarios y equipos de Active Directory.

![imagen](img/012.png)

### 1.1.6 Creación de Unidad Organizativa, Grupo y usuarios en el servidor

Tenemos que ir a herramientas administrativas, luego a usuarios y equipos.
Creamos la Unidad Organizativa.

![imagen](img/013.png)

Creamos el usuarios
![imagen](img/014.png)

Creamos el Grupo

![imagen](img/015.png)

Resultado final, creado la unidad organizativa, grupo y usuario.

![imagen](img/016.png)

## 1.2 Máquina Virtual de Windows 10
Configuramos una máquin virtual para Windows 10 como cliente para el dominio

![imagen](img/017.png)

### 1.2.1 Configuración del equipo cliente en el dominio

![imagen](img/018.png)

Sale una nueva ventana en la que debemos autorizar el acceso del equipo cliente al dominio.

![imagen](img/019.png)

Se comprueba como se une al dominio.

![imagen](img/020.png)

Comprobamos que al iniciar el Windows 10, accedemos con el usuario creado en el Servidor

![imagen](img/021.png)

Se inicia sistema operativo Windows 10 con el usuario creado en el Servidor, se comprueba que el equipo está agregado en el dominio y accede con un usuario de dominio.

![imagen](img/022.png)

# 2 Ubuntu Server
## 2.1 Configuración de la Máquina Virtual Ubuntu Server

Se crea la siguiente máquina virtual con la siguientes características.

![imagen](img/023.png)

### 2.1.1 Instalación de Ubuntu
Primeros tenemos que arrancar la iso desde la máquina virtual y seguimos el asistente de ubuntu, dejamos todos la configuración por defecto.

![imagen](img/024.png)

### 2.1.2 Configuración del nombre del equipo, usuario y contraseña.

![imagen](img/025.png)

En la siguiente imagen se ve el proceso de instalación de Ubuntu.

![imagen](img/026.png)

### 2.1.3 Configuración de la tarjeta de red

![imagen](img/027.png)

## 2.2 Configuración de la máquina virtual Ubuntu cliente

Se crea la siguiente máquina virtual con las siguientes características.

![imagen](img/028.png)
