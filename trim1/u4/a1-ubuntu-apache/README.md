# Ubuntu Servicio Web Apache2

## 1. Instalación de Apache2

Primero realizamos un update de los repositiorios de ubuntu.

```console
roberto@serverob:~$ sudo apt update
Obj:1 http://security.ubuntu.com/ubuntu xenial-security InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu xenial InRelease
Obj:3 http://es.archive.ubuntu.com/ubuntu xenial-updates InRelease
Des:4 http://es.archive.ubuntu.com/ubuntu xenial-backports InRelease [102 kB]
Descargados 102 kB en 0s (151 kB/s)                          
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se pueden actualizar 582 paquetes. Ejecute «apt list --upgradable» para verlos.
roberto@serverob:~$
```

Comenzamos a instalar el `Apache2`

```console
roberto@serverob:~$ sudo apt install apache2
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  gnome-software-common libgtkspell3-3-0
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  apache2-bin apache2-data apache2-utils libapr1 libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap liblua5.1-0
Paquetes sugeridos:
  apache2-doc apache2-suexec-pristine | apache2-suexec-custom
Se instalarán los siguientes paquetes NUEVOS:
  apache2 apache2-bin apache2-data apache2-utils libapr1 libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap liblua5.1-0
0 actualizados, 9 nuevos se instalarán, 0 para eliminar y 582 no actualizados.
Se necesita descargar 1.540 kB de archivos.
Se utilizarán 6.369 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libapr1 amd64 1.5.2-3 [86,0 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libaprutil1 amd64 1.5.4-1build1 [77,1 kB]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libaprutil1-dbd-sqlite3 amd64 1.5.4-1build1 [10,6 kB]
Des:4 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libaprutil1-ldap amd64 1.5.4-1build1 [8.720 B]
Des:5 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 liblua5.1-0 amd64 5.1.5-8ubuntu1 [102 kB]
Des:6 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 apache2-bin amd64 2.4.18-2ubuntu3.5 [925 kB]
Des:7 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 apache2-utils amd64 2.4.18-2ubuntu3.5 [82,3 kB]
Des:8 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 apache2-data all 2.4.18-2ubuntu3.5 [162 kB]
Des:9 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 apache2 amd64 2.4.18-2ubuntu3.5 [86,7 kB]
Descargados 1.540 kB en 1s (1.119 kB/s)
Seleccionando el paquete libapr1:amd64 previamente no seleccionado.
(Leyendo la base de datos ... 174439 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../libapr1_1.5.2-3_amd64.deb ...
Desempaquetando libapr1:amd64 (1.5.2-3) ...
Seleccionando el paquete libaprutil1:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libaprutil1_1.5.4-1build1_amd64.deb ...
Desempaquetando libaprutil1:amd64 (1.5.4-1build1) ...
Seleccionando el paquete libaprutil1-dbd-sqlite3:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libaprutil1-dbd-sqlite3_1.5.4-1build1_amd64.deb ...
Desempaquetando libaprutil1-dbd-sqlite3:amd64 (1.5.4-1build1) ...
Seleccionando el paquete libaprutil1-ldap:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libaprutil1-ldap_1.5.4-1build1_amd64.deb ...
Desempaquetando libaprutil1-ldap:amd64 (1.5.4-1build1) ...
Seleccionando el paquete liblua5.1-0:amd64 previamente no seleccionado.
Preparando para desempaquetar .../liblua5.1-0_5.1.5-8ubuntu1_amd64.deb ...
Desempaquetando liblua5.1-0:amd64 (5.1.5-8ubuntu1) ...
Seleccionando el paquete apache2-bin previamente no seleccionado.
Preparando para desempaquetar .../apache2-bin_2.4.18-2ubuntu3.5_amd64.deb ...
Desempaquetando apache2-bin (2.4.18-2ubuntu3.5) ...
Seleccionando el paquete apache2-utils previamente no seleccionado.
Preparando para desempaquetar .../apache2-utils_2.4.18-2ubuntu3.5_amd64.deb ...
Desempaquetando apache2-utils (2.4.18-2ubuntu3.5) ...
Seleccionando el paquete apache2-data previamente no seleccionado.
Preparando para desempaquetar .../apache2-data_2.4.18-2ubuntu3.5_all.deb ...
Desempaquetando apache2-data (2.4.18-2ubuntu3.5) ...
Seleccionando el paquete apache2 previamente no seleccionado.
Preparando para desempaquetar .../apache2_2.4.18-2ubuntu3.5_amd64.deb ...
Desempaquetando apache2 (2.4.18-2ubuntu3.5) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...
Configurando libapr1:amd64 (1.5.2-3) ...
Configurando libaprutil1:amd64 (1.5.4-1build1) ...
Configurando libaprutil1-dbd-sqlite3:amd64 (1.5.4-1build1) ...
Configurando libaprutil1-ldap:amd64 (1.5.4-1build1) ...
Configurando liblua5.1-0:amd64 (5.1.5-8ubuntu1) ...
Configurando apache2-bin (2.4.18-2ubuntu3.5) ...
Configurando apache2-utils (2.4.18-2ubuntu3.5) ...
Configurando apache2-data (2.4.18-2ubuntu3.5) ...
Configurando apache2 (2.4.18-2ubuntu3.5) ...
Enabling module mpm_event.
Enabling module authz_core.
Enabling module authz_host.
Enabling module authn_core.
Enabling module auth_basic.
Enabling module access_compat.
Enabling module authn_file.
Enabling module authz_user.
Enabling module alias.
Enabling module dir.
Enabling module autoindex.
Enabling module env.
Enabling module mime.
Enabling module negotiation.
Enabling module setenvif.
Enabling module filter.
Enabling module deflate.
Enabling module status.
Enabling conf charset.
Enabling conf localized-error-pages.
Enabling conf other-vhosts-access-log.
Enabling conf security.
Enabling conf serve-cgi-bin.
Enabling site 000-default.
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...
roberto@serverob:~$

```

Ya tenemos instalado el Apache2.

Comprobamos que tenemos la siguiente estructura de directorios y ficheros en `/var/www`

```console
roberto@serverob:~$ tree /var/www/
/var/www/
└── html
    └── index.html

1 directory, 1 file
roberto@serverob:~$
```

- Realizamos la siguiente comprobación para ver si funciona el servicio `Apache2` en el navegador.

![](img/002.png)


### 1.1 Modificación de bind9 para el nuevo dominio miempresa.edu

Tenemos que ir al fichero de configuración `/etc/bind/named.conf.local`

```console
roberto@serverob:~$ sudo cat /etc/bind/named.conf.local
#
# Do any local configuration here


# Consider adding the 1918 zones here, if they are not used in your
# organization
#include "/etc/bind/zones.rfc1918";


# Añadir en /etc/bind/named.conf.local
# Archivo para búsquedas directas

zone "skynet.edu" {
	type master;
	file "/etc/bind/db.skynet";
};

zone "miempresa.edu" {
	type master;
	file "/etc/bind/db.miempresa";
};

# Archivo para búsquedas inversas

zone "18.172.in-addr.arpa" {
	type master;
	file "/etc/bind/db.172";
};

roberto@serverob:~$

```

- Creamos un fichero llamado `db.miempresa` este fichero es la zona directa.

```console
roberto@serverob:/etc/bind$ cat db.miempresa

;
; BIND data file for local loopback interface
;
$TTL	604800
@	IN	SOA	 miempresa.edu. root.miempresa.edu. (
	2 ; Serial
	604800 ; Refresh
	86400 ; Retry
	2419200 ; Expire
	604800 ) ; Negative Cache TTL
;

@		IN	NS		miempresa.edu.
@		IN	A		172.18.22.1
@		IN	MX	0	miempresa.edu.
server		IN	A		172.18.22.1
www.miempresa.edu. IN	CNAME		miempresa.edu.
roberto@serverob:/etc/bind$
```

En la línea 18 hemos creado ya el alias para www.miempresa.edu y por lo tanto realizamos un nslookup para comprobar que funciona.

```console
roberto@serverob:/etc/bind$ nslookup www.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

www.miempresa.edu	canonical name = miempresa.edu.
Name:	miempresa.edu
Address: 172.18.22.1

roberto@serverob:/etc/bind$

```

Ya tenemos creado el nuevo dominio con su nuevo registro del alias `www.miempresa.edu` y necesitamos reiniciar el `Apache2`.

```console
roberto@serverob:/etc/bind$ sudo systemctl restart apache2.service
roberto@serverob:/etc/bind$ sudo systemctl status apache2.service
● apache2.service - LSB: Apache2 web server
   Loaded: loaded (/etc/init.d/apache2; bad; vendor preset: enabled)
  Drop-In: /lib/systemd/system/apache2.service.d
           └─apache2-systemd.conf
   Active: active (running) since mar 2017-12-05 13:32:56 WET; 15s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 9855 ExecStop=/etc/init.d/apache2 stop (code=exited, status=0/SUCCESS)
  Process: 9877 ExecStart=/etc/init.d/apache2 start (code=exited, status=0/SUCCESS)
    Tasks: 55 (limit: 512)
   CGroup: /system.slice/apache2.service
           ├─9892 /usr/sbin/apache2 -k start
           ├─9895 /usr/sbin/apache2 -k start
           └─9896 /usr/sbin/apache2 -k start

dic 05 13:32:55 serverob systemd[1]: Stopped LSB: Apache2 web server.
dic 05 13:32:55 serverob systemd[1]: Starting LSB: Apache2 web server...
dic 05 13:32:55 serverob apache2[9877]:  * Starting Apache httpd web server apache2
dic 05 13:32:55 serverob apache2[9877]: AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 127.0.1.1. Set t
dic 05 13:32:56 serverob apache2[9877]:  *
dic 05 13:32:56 serverob systemd[1]: Started LSB: Apache2 web server.
lines 1-20/20 (END)
```

- Comprobamos el navegador para ver si funciona con el nombre.

![](img/003.png)

### 1.2 Ficheros de errores en apache2

Tenemos que ir a la siguiente ruta `/var/log/apache2`

```console
roberto@serverob:/etc/bind$ sudo ls -l /var/log/apache2/
total 8
-rw-r----- 1 root adm 665 dic  5 12:49 access.log
-rw-r----- 1 root adm 681 dic  5 13:32 error.log
-rw-r----- 1 root adm   0 dic  5 12:46 other_vhosts_access.log
roberto@serverob:/etc/bind$
```

## 2. Instalación de PHP7

Solo tenemos que escribir en la terminal el siguiente comando y comienza la instalación.

```console
roberto@serverob:/etc/bind$ sudo apt install php
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  gnome-software-common libgtkspell3-3-0
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  php-common php7.0 php7.0-cli php7.0-common php7.0-fpm php7.0-json php7.0-opcache php7.0-readline
Paquetes sugeridos:
  php-pear
Se instalarán los siguientes paquetes NUEVOS:
  php php-common php7.0 php7.0-cli php7.0-common php7.0-fpm php7.0-json php7.0-opcache php7.0-readline
0 actualizados, 9 nuevos se instalarán, 0 para eliminar y 582 no actualizados.
Se necesita descargar 3.544 kB de archivos.
Se utilizarán 14,2 MB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 php-common all 1:35ubuntu6 [10,8 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-common amd64 7.0.22-0ubuntu0.16.04.1 [843 kB]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-json amd64 7.0.22-0ubuntu0.16.04.1 [16,9 kB]
Des:4 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-opcache amd64 7.0.22-0ubuntu0.16.04.1 [77,1 kB]
Des:5 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-readline amd64 7.0.22-0ubuntu0.16.04.1 [12,8 kB]
Des:6 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-cli amd64 7.0.22-0ubuntu0.16.04.1 [1.287 kB]
Des:7 http://es.archive.ubuntu.com/ubuntu xenial-updates/universe amd64 php7.0-fpm amd64 7.0.22-0ubuntu0.16.04.1 [1.293 kB]
Des:8 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0 all 7.0.22-0ubuntu0.16.04.1 [1.294 B]
Des:9 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 php all 1:7.0+35ubuntu6 [2.832 B]
Descargados 3.544 kB en 1s (3.083 kB/s)
Seleccionando el paquete php-common previamente no seleccionado.
(Leyendo la base de datos ... 175128 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../php-common_1%3a35ubuntu6_all.deb ...
Desempaquetando php-common (1:35ubuntu6) ...
Seleccionando el paquete php7.0-common previamente no seleccionado.
Preparando para desempaquetar .../php7.0-common_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-common (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0-json previamente no seleccionado.
Preparando para desempaquetar .../php7.0-json_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-json (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0-opcache previamente no seleccionado.
Preparando para desempaquetar .../php7.0-opcache_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-opcache (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0-readline previamente no seleccionado.
Preparando para desempaquetar .../php7.0-readline_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-readline (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0-cli previamente no seleccionado.
Preparando para desempaquetar .../php7.0-cli_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-cli (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0-fpm previamente no seleccionado.
Preparando para desempaquetar .../php7.0-fpm_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-fpm (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php7.0 previamente no seleccionado.
Preparando para desempaquetar .../php7.0_7.0.22-0ubuntu0.16.04.1_all.deb ...
Desempaquetando php7.0 (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php previamente no seleccionado.
Preparando para desempaquetar .../php_1%3a7.0+35ubuntu6_all.deb ...
Desempaquetando php (1:7.0+35ubuntu6) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
Configurando php-common (1:35ubuntu6) ...
Configurando php7.0-common (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/mods-available/calendar.ini with new version

Creating config file /etc/php/7.0/mods-available/ctype.ini with new version

Creating config file /etc/php/7.0/mods-available/exif.ini with new version

Creating config file /etc/php/7.0/mods-available/fileinfo.ini with new version

Creating config file /etc/php/7.0/mods-available/ftp.ini with new version

Creating config file /etc/php/7.0/mods-available/gettext.ini with new version

Creating config file /etc/php/7.0/mods-available/iconv.ini with new version

Creating config file /etc/php/7.0/mods-available/pdo.ini with new version

Creating config file /etc/php/7.0/mods-available/phar.ini with new version

Creating config file /etc/php/7.0/mods-available/posix.ini with new version

Creating config file /etc/php/7.0/mods-available/shmop.ini with new version

Creating config file /etc/php/7.0/mods-available/sockets.ini with new version

Creating config file /etc/php/7.0/mods-available/sysvmsg.ini with new version

Creating config file /etc/php/7.0/mods-available/sysvsem.ini with new version

Creating config file /etc/php/7.0/mods-available/sysvshm.ini with new version

Creating config file /etc/php/7.0/mods-available/tokenizer.ini with new version
Configurando php7.0-json (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/mods-available/json.ini with new version
Configurando php7.0-opcache (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/mods-available/opcache.ini with new version
Configurando php7.0-readline (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/mods-available/readline.ini with new version
Configurando php7.0-cli (7.0.22-0ubuntu0.16.04.1) ...
update-alternatives: utilizando /usr/bin/php7.0 para proveer /usr/bin/php (php) en modo automático
update-alternatives: utilizando /usr/bin/phar7.0 para proveer /usr/bin/phar (phar) en modo automático
update-alternatives: utilizando /usr/bin/phar.phar7.0 para proveer /usr/bin/phar.phar (phar.phar) en modo automático

Creating config file /etc/php/7.0/cli/php.ini with new version
Configurando php7.0-fpm (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/fpm/php.ini with new version
Configurando php7.0 (7.0.22-0ubuntu0.16.04.1) ...
Configurando php (1:7.0+35ubuntu6) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
roberto@serverob:/etc/bind$
```

Es necesarios instalar las siguientes librerias `sudo apt-get install libapache2-mod-php5`

```console
roberto@serverob:/etc/bind$ sudo apt install libapache2-mod-php
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  gnome-software-common libgtkspell3-3-0
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  libapache2-mod-php7.0
Paquetes sugeridos:
  php-pear
Se instalarán los siguientes paquetes NUEVOS:
  libapache2-mod-php libapache2-mod-php7.0
0 actualizados, 2 nuevos se instalarán, 0 para eliminar y 582 no actualizados.
Se necesita descargar 1.232 kB de archivos.
Se utilizarán 4.344 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libapache2-mod-php7.0 amd64 7.0.22-0ubuntu0.16.04.1 [1.229 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libapache2-mod-php all 1:7.0+35ubuntu6 [2.960 B]
Descargados 1.232 kB en 0s (1.620 kB/s)  
Seleccionando el paquete libapache2-mod-php7.0 previamente no seleccionado.
(Leyendo la base de datos ... 175275 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../libapache2-mod-php7.0_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando libapache2-mod-php7.0 (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete libapache2-mod-php previamente no seleccionado.
Preparando para desempaquetar .../libapache2-mod-php_1%3a7.0+35ubuntu6_all.deb ...
Desempaquetando libapache2-mod-php (1:7.0+35ubuntu6) ...
Configurando libapache2-mod-php7.0 (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/apache2/php.ini with new version
Module mpm_event disabled.
Enabling module mpm_prefork.
apache2_switch_mpm Switch to prefork
apache2_invoke: Enable module php7.0
Configurando libapache2-mod-php (1:7.0+35ubuntu6) ...
roberto@serverob:/etc/bind$
```

Realizamos una comprobación para ver si funciona el php, creamos un documento y desde el navegador debe ejecutarse la siguiente información de php.

![](img/004.png)

## 3. Creación de entornos virtuales

 Creamos el entorno virtual para empleados.conf

```console
roberto@serverob:/etc/apache2/sites-available$ sudo cat empleados.conf
<VirtualHost *:80>

	ServerName empleados.miempresa.com
	DocumentRoot /var/www/empleados

</VirtualHost>
roberto@serverob:/etc/apache2/sites-available$
```

Creamos el entorno virtual para pagos.conf

```console
roberto@serverob:/etc/apache2/sites-available$ cat pagos.conf
<VirtualHost *:80>

	ServerName pagos.miempresa.com
	DocumentRoot /var/www/pagos

</VirtualHost>
roberto@serverob:/etc/apache2/sites-available$
```

Creamos el entorno virtual para phpmyadmin

```console
roberto@serverob:/etc/apache2/sites-available$ cat phpmyadmin.conf
<VirtualHost *:80>

	ServerName phpmyadmin.miempresa.com
	DocumentRoot /var/www/phpmyadmin

</VirtualHost>
roberto@serverob:/etc/apache2/sites-available$

```
Tenemos que añadir en el servicio de DNS los registros de phpmyadmin y pagos.

```console
roberto@serverob:/etc/bind$ cat db.miempresa

;
; BIND data file for local loopback interface
;
$TTL	604800
@	IN	SOA	 miempresa.edu. root.miempresa.edu. (
	2 ; Serial
	604800 ; Refresh
	86400 ; Retry
	2419200 ; Expire
	604800 ) ; Negative Cache TTL
;

@		IN	NS		miempresa.edu.
@		IN	A		172.18.22.1
@		IN	MX	0	miempresa.edu.
server		IN	A		172.18.22.1
www.miempresa.edu. IN	CNAME		miempresa.edu.
pagos.miempresa.edu IN	CNAME		miempresa.edu.
phpmyadmin.miempresa.edu IN	CNAME	miempresa.edu.
roberto@serverob:/etc/bind$
```

Realizamos un nslookup para ver si funciona correctamente.

```console

roberto@serverob:/etc/bind$ nslookup pagos.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

pagos.miempresa.edu	canonical name = miempresa.edu.
Name:	miempresa.edu
Address: 172.18.22.1

roberto@serverob:/etc/bind$ nslookup phpmyadmin.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

phpmyadmin.miempresa.edu	canonical name = miempresa.edu.
Name:	miempresa.edu
Address: 172.18.22.1

roberto@serverob:/etc/bind$

```
Creamos los directorios.

```console
roberto@serverob:/var/www$ sudo mkdir empleados pagos phpmyadmin
[sudo] password for roberto:
Lo sentimos, vuelva a intentarlo.
[sudo] password for roberto:
roberto@serverob:/var/www$ ls -l
total 16
drwxr-xr-x 2 root root 4096 dic  6 23:01 empleados
drwxr-xr-x 2 root root 4096 dic  5 13:45 html
drwxr-xr-x 2 root root 4096 dic  6 23:01 pagos
drwxr-xr-x 2 root root 4096 dic  6 23:01 phpmyadmin
roberto@serverob:/var/www$
```

## 4. Configurar sitio web seguro pagos.

Lo primero que tenemos que realizar es generar unos certificados autofirmado.

```console
roberto@serverob:~$ openssl genrsa -des3 -out server.key 1024
Generating RSA private key, 1024 bit long modulus
.....++++++
..++++++
e is 65537 (0x10001)
Enter pass phrase for server.key:
Verifying - Enter pass phrase for server.key:
roberto@serverob:~$ ls
Descargas   Escritorio        Imágenes  Plantillas  server.key
Documentos  examples.desktop  Música    Público     Vídeos
roberto@serverob:~$ cat server.key
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: DES-EDE3-CBC,F463A0D18F2785A1

zIA6l+o5477IQYQEIgNMjhUhVSUqueLozuSMVYijyK2rsBlI44C9/Pegk3yV0mxQ
/616Skpjs4FCjjP722D0yej4lOP2r0xJcvgCJoGjzbplPGmpY7SDt0Q8QrIk/K5S
aU3eR23z7Ez9ASByaCxLVg2tW3VFqWHo393PEoCqib5lXcGB+d9ERFKAozcX660X
eUR6/WOR/aH+IqNRCEj+tTP4Y8WSqxhpzNcfZ2psQcE8BuHslNCGIK4yngDfu0T7
8uCb7ZcYkVZEZSEmaW4H9nv1dDXbhbMcGwCiUn5YqJnBYUq2R0o8SWPuUecVxTta
zFNCFrhG71C1Z6gCvW4LYsSRwm5E+5HPpe9r+WFidY097EYfZv+f1Jj9sK2hjGTs
xN/KxE8Zfly5UcisxTytidjnKOVb6LEgfx4f+7cFfH7/ForgaWn1zn3vYwkC7tZR
61Q4m0luCsevdsv1g1XWw7S3DviWfQdDpc2C95o7QZ1ythxSlgjCkdFOvYJVNlg7
vTsqnEV8qmPQd7TmZ+YGiTe9k5EgxbsfcZF07SZa23WGrmyHLZF/q36pOOPo6iCa
rc0DW3pScdnYIuvsWux1QavmAx4l0YeyckcXgjD/0LX+24xQ/vCBbpVvMXBHgUKH
3EjeXswWI/5nwv1pP0xeBiwSpoAVDw9YSMJu+6fMJjEox/TWeVIILs/DYLG8lD+A
dh1z1N5rYAxPNkJfs5PzzAO7G/N0yGbpZ8IqSUpxgUczyC0U6eC3qSUN9w+9NEbm
q9VnSUEdsQBcHdOB90cijv+iTF7ntCOKsdZ3o99/ud+0vi9htOK6nQ==
-----END RSA PRIVATE KEY-----
roberto@serverob:~$ openssl rsa -in server.key -out server.pem
Enter pass phrase for server.key:
writing RSA key
roberto@serverob:~$ openssl req -new -key server.key -out server.csr
Enter pass phrase for server.key:
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:ES
State or Province Name (full name) [Some-State]:Santa Cruz de Tenerife
Locality Name (eg, city) []:Los Realejos
Organization Name (eg, company) [Internet Widgits Pty Ltd]:miempresa.edu
Organizational Unit Name (eg, section) []:empresa
Common Name (e.g. server FQDN or YOUR name) []:empresa
Email Address []:miempresa@edu.com

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
roberto@serverob:~$ openssl x509 -req -days 360 -in server.csr -signkey server.key -out server.crt
Signature ok
subject=/C=ES/ST=Santa Cruz de Tenerife/L=Los Realejos/O=miempresa.edu/OU=empresa/CN=empresa/emailAddress=miempresa@edu.com
Getting Private key
Enter pass phrase for server.key:
roberto@serverob:~$

```

Tenemos que copiar el certificado a la siguiente ruta `/etc/apache2`

```console
roberto@serverob:~$ ls
Descargas   examples.desktop  Plantillas  server.csr  Vídeos
Documentos  Imágenes          Público     server.key
Escritorio  Música            server.crt  server.pem
roberto@serverob:~$ sudo cp server.key /etc/apache2/
[sudo] password for roberto:
roberto@serverob:~$ sudo cp server.crt /etc/apache2/
roberto@serverob:~$ ls -l /etc/apache2/
total 88
-rw-r--r-- 1 root root  7115 mar 19  2016 apache2.conf
drwxr-xr-x 2 root root  4096 dic  5 13:41 conf-available
drwxr-xr-x 2 root root  4096 dic  5 12:46 conf-enabled
-rw-r--r-- 1 root root  1782 mar 19  2016 envvars
-rw-r--r-- 1 root root 31063 mar 19  2016 magic
drwxr-xr-x 2 root root 12288 dic  5 13:45 mods-available
drwxr-xr-x 2 root root  4096 dic  5 13:46 mods-enabled
-rw-r--r-- 1 root root   320 mar 19  2016 ports.conf
-rw-r--r-- 1 root root  1013 dic 12 12:44 server.crt
-rw-r--r-- 1 root root   963 dic 12 12:44 server.key
drwxr-xr-x 2 root root  4096 dic 12 12:41 sites-available
drwxr-xr-x 2 root root  4096 dic 12 12:43 sites-enabled
roberto@serverob:~$
```

Tenemos que crear o modificar el fichero de virtual host de apache2 en sities-available.

```console
roberto@serverob:/etc/apache2/sites-available$ cat pagos.conf
<VirtualHost *:443>

	ServerName pagos.miempresa.com
	DocumentRoot /var/www/pagos
	SSLEngine On
	SSLCertificateFile /etc/apache2/server.crt
	SSLCertificateKeyFile /etc/apache2/server.key
	ErrorLog /var/log/apache2/ssl.error.log
	CustomLog /var/log/apache2/ssl.access.log combined

	<Directory /var/www/pagos>
		Options Indexes FollowSymLinks MultiViews
		AllowOverride None
		Order allow,deny
		allow from all
		SSLRequiereSSL
	</Directory>
</VirtualHost>
roberto@serverob:/etc/apache2/sites-available$
```
Para crear el enlace simbólico solo tenemos que escribir el siguiente comando.

```console
roberto@serverob:/etc/apache2/sites-available$ sudo a2ensite pagos.conf
Enabling site pagos.
To activate the new configuration, you need to run:
  service apache2 reload
```

- Tenemos que habilitar el SSL con el siguiente comando.

```console
roberto@serverob:/etc/apache2/sites-available$ sudo a2enmod ssl
Considering dependency setenvif for ssl:
Module setenvif already enabled
Considering dependency mime for ssl:
Module mime already enabled
Considering dependency socache_shmcb for ssl:
Enabling module socache_shmcb.
Enabling module ssl.
See /usr/share/doc/apache2/README.Debian.gz on how to configure SSL and create self-signed certificates.
To activate the new configuration, you need to run:
  service apache2 restart
roberto@serverob:/etc/apache2/sites-available$
```
- Reiniciamos el servicio de apache2

```console
roberto@serverob:/etc/apache2/sites-available$ sudo systemctl restart apache2.service
Enter passphrase for SSL/TLS keys for pagos.miempresa.com:443 (RSA): *********
roberto@serverob:/etc/apache2/sites-available$ sudo systemctl status apache2.service
● apache2.service - LSB: Apache2 web server
   Loaded: loaded (/etc/init.d/apache2; bad; vendor preset: enabled)
  Drop-In: /lib/systemd/system/apache2.service.d
           └─apache2-systemd.conf
   Active: active (running) since mar 2017-12-12 12:57:23 WET; 13s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 3488 ExecStop=/etc/init.d/apache2 stop (code=exited, status=0/SUCCESS)
  Process: 3728 ExecStart=/etc/init.d/apache2 start (code=exited, status=0/SUCCESS)
    Tasks: 6 (limit: 512)
   CGroup: /system.slice/apache2.service
           ├─3754 /usr/sbin/apache2 -k start
           ├─3757 /usr/sbin/apache2 -k start
           ├─3758 /usr/sbin/apache2 -k start
           ├─3759 /usr/sbin/apache2 -k start
           ├─3760 /usr/sbin/apache2 -k start
           └─3761 /usr/sbin/apache2 -k start

dic 12 12:57:11 serverob systemd[1]: Stopped LSB: Apache2 web server.
dic 12 12:57:11 serverob systemd[1]: Starting LSB: Apache2 web server...
dic 12 12:57:11 serverob apache2[3728]:  * Starting Apache httpd web server apache2
dic 12 12:57:12 serverob apache2[3728]: AH00558: apache2: Could not reliably determine the server's fully qualified domain
dic 12 12:57:23 serverob apache2[3728]:  *
dic 12 12:57:23 serverob systemd[1]: Started LSB: Apache2 web server.
lines 1-23/23 (END)
```
- Creamos un index.html en la siguiente ruta `/var/www/pagos`

```console

roberto@serverob:/var/www/pagos$ sudo nano index.html
roberto@serverob:/var/www/pagos$ ls -l
total 4
-rw-r--r-- 1 root root 28 dic 12 12:58 index.html
roberto@serverob:/var/www/pagos$
```

- Abrimos un navegador y comprobamos que funciona el `https`

![](img/005.png)

![](img/006.png)

![](img/007.png)


## Carpetas Privadas

```console
roberto@serverob:/etc/apache2$ ls -la
total 104
drwxr-xr-x   8 root root  4096 dic 12 13:27 .
drwxr-xr-x 133 root root 12288 dic 12 12:20 ..
-rw-r--r--   1 root root  7115 mar 19  2016 apache2.conf
drwxr-xr-x   2 root root  4096 dic  5 13:41 conf-available
drwxr-xr-x   2 root root  4096 dic  5 12:46 conf-enabled
-rw-r--r--   1 root root  1782 mar 19  2016 envvars
-rw-r--r--   1 root root     0 dic 12 13:27 .htpasswd
-rw-r--r--   1 root root 31063 mar 19  2016 magic
drwxr-xr-x   2 root root 12288 dic  5 13:45 mods-available
drwxr-xr-x   2 root root  4096 dic 12 12:54 mods-enabled
-rw-r--r--   1 root root   320 mar 19  2016 ports.conf
-rw-r--r--   1 root root  1013 dic 12 12:44 server.crt
-rw-r--r--   1 root root   963 dic 12 12:44 server.key
drwxr-xr-x   2 root root  4096 dic 12 13:18 sites-available
drwxr-xr-x   2 root root  4096 dic 12 12:43 sites-enabled
roberto@serverob:/etc/apache2$ htpasswd -c .htpasswd kevin
htpasswd: cannot open file .htpasswd for read/write access
roberto@serverob:/etc/apache2$ sudo htpasswd -c .htpasswd kevin
New password:
Re-type new password:
Adding password for user kevin
roberto@serverob:/etc/apache2$ sudo htpasswd .htpasswd admin
New password:
Re-type new password:
Adding password for user admin
roberto@serverob:/etc/apache2$ sudo cat .htpasswd
kevin:$apr1$qNKaXYhX$M2HFlWueH3D5fIJldAito/
admin:$apr1$Jw.NS8cg$WpO2Hc7.gloX7q9hu9Jrq0
roberto@serverob:/etc/apache2$
```
