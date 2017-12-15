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

Tenemos que crear y escribir dentro de .htaccess los siguiente.

```console
roberto@serverob:/var/www/empleados$ cat .htaccess
AuthName "Es necesario Autentificarse"
AuthType Basic
AuthUserFile /var/www/empleados
require valid-user
roberto@serverob:/var/www/empleados$

```
Tenemos que crear las siguientes contraseñas y usuarios y el fichero se llamara .htpasswd.

```console
roberto@serverob:/var/www/empleados$ sudo htpasswd -c .htpasswd kevin
New password:
Re-type new password:
Adding password for user kevin
roberto@serverob:/var/www/empleados$ sudo htpasswd .htpasswd roberto
New password:
Re-type new password:
Adding password for user roberto
roberto@serverob:/var/www/empleados$ sudo htpasswd .htpasswd oscar
New password:
Re-type new password:
Adding password for user oscar

```
Comprobamos con el comando tree -a para visualizar todo los ficheros de configuración creados.

```console
roberto@serverob:/var/www/empleados$ tree -a
.
├── comercial
│   ├── .htaccess
│   └── .htpasswd
├── .htaccess
├── .htpasswd
├── index.html
├── tecnico
│   ├── .htaccess
│   └── .htpasswd
└── tienda
    ├── .htaccess
    └── .htpasswd

3 directories, 9 files
roberto@serverob:/var/www/empleados$

```

## 6. Instalación de MySQL

Tenemos que instalar la base de datos de MySQL.

```console
roberto@serverob:~$ sudo apt install mysql-server
[sudo] password for roberto:
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  libaio1 libevent-core-2.0-5 libhtml-template-perl mysql-client-5.7
  mysql-client-core-5.7 mysql-common mysql-server-5.7 mysql-server-core-5.7
Paquetes sugeridos:
  libipc-sharedcache-perl mailx tinyca
Se instalarán los siguientes paquetes NUEVOS:
  libaio1 libevent-core-2.0-5 libhtml-template-perl mysql-client-5.7
  mysql-client-core-5.7 mysql-common mysql-server mysql-server-5.7
  mysql-server-core-5.7
0 actualizados, 9 nuevos se instalarán, 0 para eliminar y 369 no actualizados.
Se necesita descargar 18,6 MB de archivos.
Se utilizarán 161 MB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-common all 5.7.20-0ubuntu0.16.04.1 [15,6 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libaio1 amd64 0.3.110-2 [6.356 B]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-client-core-5.7 amd64 5.7.20-0ubuntu0.16.04.1 [6.339 kB]
Des:4 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-client-5.7 amd64 5.7.20-0ubuntu0.16.04.1 [1.675 kB]
Des:5 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-server-core-5.7 amd64 5.7.20-0ubuntu0.16.04.1 [7.670 kB]
Des:6 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libevent-core-2.0-5 amd64 2.0.21-stable-2ubuntu0.16.04.1 [70,6 kB]
Des:7 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-server-5.7 amd64 5.7.20-0ubuntu0.16.04.1 [2.708 kB]
Des:8 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libhtml-template-perl all 2.95-2 [60,4 kB]
Des:9 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-server all 5.7.20-0ubuntu0.16.04.1 [10,2 kB]
Descargados 18,6 MB en 3s (4.958 kB/s)
Preconfigurando paquetes ...
Seleccionando el paquete mysql-common previamente no seleccionado.
(Leyendo la base de datos ... 208018 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../mysql-common_5.7.20-0ubuntu0.16.04.1_all.deb ...
Desempaquetando mysql-common (5.7.20-0ubuntu0.16.04.1) ...
Seleccionando el paquete libaio1:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libaio1_0.3.110-2_amd64.deb ...
Desempaquetando libaio1:amd64 (0.3.110-2) ...
Seleccionando el paquete mysql-client-core-5.7 previamente no seleccionado.
Preparando para desempaquetar .../mysql-client-core-5.7_5.7.20-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando mysql-client-core-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Seleccionando el paquete mysql-client-5.7 previamente no seleccionado.
Preparando para desempaquetar .../mysql-client-5.7_5.7.20-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando mysql-client-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Seleccionando el paquete mysql-server-core-5.7 previamente no seleccionado.
Preparando para desempaquetar .../mysql-server-core-5.7_5.7.20-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando mysql-server-core-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Seleccionando el paquete libevent-core-2.0-5:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libevent-core-2.0-5_2.0.21-stable-2ubuntu0.16.04.1_amd64.deb ...
Desempaquetando libevent-core-2.0-5:amd64 (2.0.21-stable-2ubuntu0.16.04.1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu9) ...
Procesando disparadores para man-db (2.7.5-1) ...
Configurando mysql-common (5.7.20-0ubuntu0.16.04.1) ...
update-alternatives: utilizando /etc/mysql/my.cnf.fallback para proveer /etc/mysql/my.cnf (my.cnf) en modo automático
Seleccionando el paquete mysql-server-5.7 previamente no seleccionado.
(Leyendo la base de datos ... 208186 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../mysql-server-5.7_5.7.20-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando mysql-server-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Seleccionando el paquete libhtml-template-perl previamente no seleccionado.
Preparando para desempaquetar .../libhtml-template-perl_2.95-2_all.deb ...
Desempaquetando libhtml-template-perl (2.95-2) ...
Seleccionando el paquete mysql-server previamente no seleccionado.
Preparando para desempaquetar .../mysql-server_5.7.20-0ubuntu0.16.04.1_all.deb ...
Desempaquetando mysql-server (5.7.20-0ubuntu0.16.04.1) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Configurando libaio1:amd64 (0.3.110-2) ...
Configurando mysql-client-core-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Configurando mysql-client-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Configurando mysql-server-core-5.7 (5.7.20-0ubuntu0.16.04.1) ...
Configurando libevent-core-2.0-5:amd64 (2.0.21-stable-2ubuntu0.16.04.1) ...
Configurando mysql-server-5.7 (5.7.20-0ubuntu0.16.04.1) ...
update-alternatives: utilizando /etc/mysql/mysql.cnf para proveer /etc/mysql/my.cnf (my.cnf) en modo automático
Renaming removed key_buffer and myisam-recover options (if present)
Configurando libhtml-template-perl (2.95-2) ...
Configurando mysql-server (5.7.20-0ubuntu0.16.04.1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu9) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
roberto@serverob:~$
```
Ya tenemos instalado la base de datos de MySQL.

- Instalamos el siguiente soporte para php

```console
roberto@serverob:~$ sudo apt install php-mysql
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  php7.0-mysql
Se instalarán los siguientes paquetes NUEVOS:
  php-mysql php7.0-mysql
0 actualizados, 2 nuevos se instalarán, 0 para eliminar y 369 no actualizados.
Se necesita descargar 126 kB de archivos.
Se utilizarán 497 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 php7.0-mysql amd64 7.0.22-0ubuntu0.16.04.1 [124 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 php-mysql all 1:7.0+35ubuntu6 [1.936 B]
Descargados 126 kB en 0s (221 kB/s)
Seleccionando el paquete php7.0-mysql previamente no seleccionado.
(Leyendo la base de datos ... 208287 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../php7.0-mysql_7.0.22-0ubuntu0.16.04.1_amd64.deb ...
Desempaquetando php7.0-mysql (7.0.22-0ubuntu0.16.04.1) ...
Seleccionando el paquete php-mysql previamente no seleccionado.
Preparando para desempaquetar .../php-mysql_1%3a7.0+35ubuntu6_all.deb ...
Desempaquetando php-mysql (1:7.0+35ubuntu6) ...
Procesando disparadores para libapache2-mod-php7.0 (7.0.22-0ubuntu0.16.04.1) ...
Procesando disparadores para php7.0-fpm (7.0.22-0ubuntu0.16.04.1) ...
Configurando php7.0-mysql (7.0.22-0ubuntu0.16.04.1) ...

Creating config file /etc/php/7.0/mods-available/mysqlnd.ini with new version

Creating config file /etc/php/7.0/mods-available/mysqli.ini with new version

Creating config file /etc/php/7.0/mods-available/pdo_mysql.ini with new version
Configurando php-mysql (1:7.0+35ubuntu6) ...
Procesando disparadores para libapache2-mod-php7.0 (7.0.22-0ubuntu0.16.04.1) ...
Procesando disparadores para php7.0-fpm (7.0.22-0ubuntu0.16.04.1) ...
roberto@serverob:~$

```
## 7. Instalación de PHPMyAdmin.

Tenemos que ir a la página de PHPMyAdmin y instalamos la última versión en la siguiente ruta. <a name="https://www.phpmyadmin.net/downloads/">PHPMyAdmin</a>

![](img/009.png)

Tenemos descargado el fichero lo descomprimimos y le damos permisos de root y los movemos `/var/www`

```console
roberto@serverob:~/Descargas$ ls
phpMyAdmin-4.7.6-all-languages  phpMyAdmin-4.7.6-all-languages.zip
roberto@serverob:~/Descargas$ mv phpMyAdmin-4.7.6-all-languages phpmyadmin
roberto@serverob:~/Descargas$ sudo mv phpmyadmin /var/www/
roberto@serverob:~/Descargas$ ls -l /var/www/
total 16
drwxr-xr-x  5 root    root    4096 dic 14 08:41 empleados
drwxr-xr-x  2 root    root    4096 dic  5 13:45 html
drwxr-xr-x  2 root    root    4096 dic 12 12:58 pagos
drwxr-xr-x 12 roberto roberto 4096 nov 29 19:21 phpmyadmin
roberto@serverob:~/Descargas$ sudo chown root:root /var/www/phpmyadmin/
roberto@serverob:~/Descargas$ ls -l /var/www/
total 16
drwxr-xr-x  5 root root 4096 dic 14 08:41 empleados
drwxr-xr-x  2 root root 4096 dic  5 13:45 html
drwxr-xr-x  2 root root 4096 dic 12 12:58 pagos
drwxr-xr-x 12 root root 4096 nov 29 19:21 phpmyadmin
roberto@serverob:~/Descargas$
```

- Tenemos que crear un virtual host para phpmyadmin y crear un enlace simbolico en /etc/apache2/sities-enable

```console
oberto@serverob:/var/www$ sudo ln -s /etc/apache2/sites-available/phpmyadmin.conf /etc/apache2/sites-enabled/
roberto@serverob:/var/www$ sudo cat /etc/apache2/sites-available/phpmyadmin.conf
<VirtualHost *:80>

	ServerName phpmyadmin.miempresa.edu
	DocumentRoot /var/www/phpmyadmin

</VirtualHost>
roberto@serverob:/var/www$
```
- Reiniciamos el servicio de apache2

```console
roberto@serverob:/var/www$ sudo systemctl restart apache2
Enter passphrase for SSL/TLS keys for pagos.miempresa.com:443 (RSA): *********
roberto@serverob:/var/www$ sudo systemctl status apache2
● apache2.service - LSB: Apache2 web server
   Loaded: loaded (/etc/init.d/apache2; bad; vendor preset: enabled)
  Drop-In: /lib/systemd/system/apache2.service.d
           └─apache2-systemd.conf
   Active: active (running) since vie 2017-12-15 08:38:04 WET; 7s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 18484 ExecStop=/etc/init.d/apache2 stop (code=exited, status=0/SUCCES
  Process: 18507 ExecStart=/etc/init.d/apache2 start (code=exited, status=0/SUCC
   CGroup: /system.slice/apache2.service
           ├─18467 /usr/sbin/apache2 -k start
           ├─18468 /usr/sbin/apache2 -k start
           ├─18469 /usr/sbin/apache2 -k start
           ├─18470 /usr/sbin/apache2 -k start
           ├─18471 /usr/sbin/apache2 -k start
           ├─18472 /usr/sbin/apache2 -k start
           ├─18526 /usr/sbin/apache2 -k start
           ├─18528 /usr/sbin/apache2 -k start
           ├─18529 /usr/sbin/apache2 -k start
           ├─18530 /usr/sbin/apache2 -k start
           ├─18531 /usr/sbin/apache2 -k start
           └─18532 /usr/sbin/apache2 -k start

dic 15 08:37:58 serverob systemd[1]: Stopped LSB: Apache2 web server.
dic 15 08:37:58 serverob systemd[1]: Starting LSB: Apache2 web server...
dic 15 08:37:58 serverob apache2[18507]:  * Starting Apache httpd web server apa
dic 15 08:37:58 serverob apache2[18507]: AH00558: apache2: Could not reliably de
dic 15 08:38:04 serverob apache2[18507]:  *
dic 15 08:38:04 serverob systemd[1]: Started LSB: Apache2 web server.
roberto@serverob:/var/www$
```

- Comprobamos con un navegador que podemos ver la aplicación por web de `phpmyadmin`



## Instalación de Wordpress

Tenemos que ir a la página oficial de Wordpress y descargamos la aplicación.

Ya tenemos descargado la aplicación solo debemos descomprimir la aplicación en la siguiente ruta `/var/www/html`

```console
roberto@serverob:/var/www/html$ sudo unzip /home/roberto/Descargas/wordpress-4.9.1-es_ES.zip
Archive:  /home/roberto/Descargas/wordpress-4.9.1-es_ES.zip
   creating: wordpress/
  inflating: wordpress/wp-mail.php   
  inflating: wordpress/wp-cron.php   
  inflating: wordpress/wp-trackback.php  
  inflating: wordpress/wp-activate.php  
  inflating: wordpress/xmlrpc.php    
   creating: wordpress/wp-content/
 extracting: wordpress/wp-content/index.php  
   creating: wordpress/wp-content/languages/
  inflating: wordpress/wp-content/languages/admin-network-es_ES.mo  
  inflating: wordpress/wp-content/languages/continents-cities-es_ES.po  
  inflating: wordpress/wp-content/languages/continents-cities-es_ES.mo  
  inflating: wordpress/wp-content/languages/es_ES.mo  
  inflating: wordpress/wp-content/languages/es_ES.po  
  inflating: wordpress/wp-content/languages/admin-network-es_ES.po  
   creating: wordpress/wp-content/languages/themes/
  inflating: wordpress/wp-content/languages/themes/twentyfifteen-es_ES.po  
  inflating: wordpress/wp-content/languages/themes/twentysixteen-es_ES.mo  
  inflating: wordpress/wp-content/languages/themes/twentysixteen-es_ES.po  
  inflating: wordpress/wp-content/languages/themes/twentyseventeen-es_ES.po  
  inflating: wordpress/wp-content/languages/themes/twentyseventeen-es_ES.mo  
  inflating: wordpress/wp-content/languages/themes/twentyfifteen-es_ES.mo  
  inflating: wordpress/wp-content/languages/admin-es_ES.po  
  inflating: wordpress/wp-content/languages/admin-es_ES.mo  
   creating: wordpress/wp-content/languages/plugins/
  inflating: wordpress/wp-content/languages/plugins/akismet-es_ES.mo  
  inflating: wordpress/wp-content/languages/plugins/akismet-es_ES.po  
   creating: wordpress/wp-content/themes/
   creating: wordpress/wp-content/themes/twentysixteen/
  inflating: wordpress/wp-content/themes/twentysixteen/sidebar-content-bottom.php  
  inflating: wordpress/wp-content/themes/twentysixteen/readme.txt  
   creating: wordpress/wp-content/themes/twentysixteen/template-parts/
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/content-search.php  
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/content-single.php  
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/content-none.php  
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/biography.php  
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/content-page.php  
  inflating: wordpress/wp-content/themes/twentysixteen/template-parts/content.php  
  inflating: wordpress/wp-content/themes/twentysixteen/screenshot.png  
   creating: wordpress/wp-content/themes/twentysixteen/inc/
  inflating: wordpress/wp-content/themes/twentysixteen/inc/template-tags.php  
  inflating: wordpress/wp-content/themes/twentysixteen/inc/customizer.php  
  inflating: wordpress/wp-content/themes/twentysixteen/inc/back-compat.php  
  inflating: wordpress/wp-content/themes/twentysixteen/search.php  
  inflating: wordpress/wp-content/themes/twentysixteen/404.php  
  inflating: wordpress/wp-content/themes/twentysixteen/page.php  
  inflating: wordpress/wp-content/themes/twentysixteen/sidebar.php  
  inflating: wordpress/wp-content/themes/twentysixteen/comments.php  
  inflating: wordpress/wp-content/themes/twentysixteen/single.php  
   creating: wordpress/wp-content/themes/twentysixteen/js/
  inflating: wordpress/wp-content/themes/twentysixteen/js/keyboard-image-navigation.js  
  inflating: wordpress/wp-content/themes/twentysixteen/js/functions.js  
  inflating: wordpress/wp-content/themes/twentysixteen/js/skip-link-focus-fix.js  
  inflating: wordpress/wp-content/themes/twentysixteen/js/color-scheme-control.js  
  inflating: wordpress/wp-content/themes/twentysixteen/js/html5.js  
  inflating: wordpress/wp-content/themes/twentysixteen/js/customize-preview.js  
  inflating: wordpress/wp-content/themes/twentysixteen/index.php  
  inflating: wordpress/wp-content/themes/twentysixteen/header.php  
  inflating: wordpress/wp-content/themes/twentysixteen/image.php  
  inflating: wordpress/wp-content/themes/twentysixteen/functions.php  
   creating: wordpress/wp-content/themes/twentysixteen/genericons/
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/LICENSE.txt  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/Genericons.woff  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/Genericons.eot  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/COPYING.txt  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/README.md  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/Genericons.ttf  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/genericons.css  
  inflating: wordpress/wp-content/themes/twentysixteen/genericons/Genericons.svg  
  inflating: wordpress/wp-content/themes/twentysixteen/searchform.php  
  inflating: wordpress/wp-content/themes/twentysixteen/rtl.css  
  inflating: wordpress/wp-content/themes/twentysixteen/style.css  
  inflating: wordpress/wp-content/themes/twentysixteen/footer.php  
  inflating: wordpress/wp-content/themes/twentysixteen/archive.php  
   creating: wordpress/wp-content/themes/twentysixteen/css/
  inflating: wordpress/wp-content/themes/twentysixteen/css/ie.css  
  inflating: wordpress/wp-content/themes/twentysixteen/css/editor-style.css  
  inflating: wordpress/wp-content/themes/twentysixteen/css/ie8.css  
  inflating: wordpress/wp-content/themes/twentysixteen/css/ie7.css  
 extracting: wordpress/wp-content/themes/index.php  
   creating: wordpress/wp-content/themes/twentyfifteen/
  inflating: wordpress/wp-content/themes/twentyfifteen/content-search.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/readme.txt  
  inflating: wordpress/wp-content/themes/twentyfifteen/content-none.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/screenshot.png  
   creating: wordpress/wp-content/themes/twentyfifteen/inc/
  inflating: wordpress/wp-content/themes/twentyfifteen/inc/template-tags.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/inc/customizer.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/inc/custom-header.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/inc/back-compat.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/search.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/404.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/page.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/sidebar.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/comments.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/single.php  
   creating: wordpress/wp-content/themes/twentyfifteen/js/
  inflating: wordpress/wp-content/themes/twentyfifteen/js/keyboard-image-navigation.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/js/functions.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/js/skip-link-focus-fix.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/js/color-scheme-control.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/js/html5.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/js/customize-preview.js  
  inflating: wordpress/wp-content/themes/twentyfifteen/content-page.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/index.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/content.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/header.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/image.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/functions.php  
   creating: wordpress/wp-content/themes/twentyfifteen/genericons/
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/LICENSE.txt  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/Genericons.woff  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/Genericons.eot  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/COPYING.txt  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/README.md  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/Genericons.ttf  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/genericons.css  
  inflating: wordpress/wp-content/themes/twentyfifteen/genericons/Genericons.svg  
  inflating: wordpress/wp-content/themes/twentyfifteen/rtl.css  
  inflating: wordpress/wp-content/themes/twentyfifteen/style.css  
  inflating: wordpress/wp-content/themes/twentyfifteen/content-link.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/author-bio.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/footer.php  
  inflating: wordpress/wp-content/themes/twentyfifteen/archive.php  
   creating: wordpress/wp-content/themes/twentyfifteen/css/
  inflating: wordpress/wp-content/themes/twentyfifteen/css/ie.css  
  inflating: wordpress/wp-content/themes/twentyfifteen/css/editor-style.css  
  inflating: wordpress/wp-content/themes/twentyfifteen/css/ie7.css  
   creating: wordpress/wp-content/themes/twentyseventeen/
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/footer/
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/footer/footer-widgets.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/footer/site-info.php  
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/navigation/
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/navigation/navigation-top.php  
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/header/
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/header/site-branding.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/header/header-image.php  
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/page/
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/page/content-front-page-panels.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/page/content-page.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/page/content-front-page.php  
   creating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-none.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-audio.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-video.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-excerpt.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-image.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/template-parts/post/content-gallery.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/screenshot.png  
   creating: wordpress/wp-content/themes/twentyseventeen/inc/
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/template-tags.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/customizer.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/custom-header.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/template-functions.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/back-compat.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/icon-functions.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/inc/color-patterns.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/search.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/404.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/README.txt  
  inflating: wordpress/wp-content/themes/twentyseventeen/page.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/sidebar.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/comments.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/single.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/index.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/header.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/functions.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/searchform.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/rtl.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/style.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/front-page.php  
   creating: wordpress/wp-content/themes/twentyseventeen/assets/
   creating: wordpress/wp-content/themes/twentyseventeen/assets/js/
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/global.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/customize-controls.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/skip-link-focus-fix.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/jquery.scrollTo.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/html5.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/customize-preview.js  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/js/navigation.js  
   creating: wordpress/wp-content/themes/twentyseventeen/assets/images/
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/images/header.jpg  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/images/espresso.jpg  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/images/sandwich.jpg  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/images/coffee.jpg  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/images/svg-icons.svg  
   creating: wordpress/wp-content/themes/twentyseventeen/assets/css/
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/css/ie9.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/css/colors-dark.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/css/editor-style.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/assets/css/ie8.css  
  inflating: wordpress/wp-content/themes/twentyseventeen/footer.php  
  inflating: wordpress/wp-content/themes/twentyseventeen/archive.php  
   creating: wordpress/wp-content/plugins/
 extracting: wordpress/wp-content/plugins/index.php  
   creating: wordpress/wp-content/plugins/akismet/
  inflating: wordpress/wp-content/plugins/akismet/readme.txt  
  inflating: wordpress/wp-content/plugins/akismet/LICENSE.txt  
  inflating: wordpress/wp-content/plugins/akismet/class.akismet-rest-api.php  
  inflating: wordpress/wp-content/plugins/akismet/class.akismet-cli.php  
   creating: wordpress/wp-content/plugins/akismet/views/
  inflating: wordpress/wp-content/plugins/akismet/views/get.php  
  inflating: wordpress/wp-content/plugins/akismet/views/config.php  
  inflating: wordpress/wp-content/plugins/akismet/views/stats.php  
  inflating: wordpress/wp-content/plugins/akismet/views/notice.php  
  inflating: wordpress/wp-content/plugins/akismet/views/start.php  
  inflating: wordpress/wp-content/plugins/akismet/class.akismet-admin.php  
 extracting: wordpress/wp-content/plugins/akismet/index.php  
   creating: wordpress/wp-content/plugins/akismet/_inc/
  inflating: wordpress/wp-content/plugins/akismet/_inc/akismet.js  
  inflating: wordpress/wp-content/plugins/akismet/_inc/akismet.css  
  inflating: wordpress/wp-content/plugins/akismet/_inc/form.js  
   creating: wordpress/wp-content/plugins/akismet/_inc/img/
  inflating: wordpress/wp-content/plugins/akismet/_inc/img/logo-full-2x.png  
  inflating: wordpress/wp-content/plugins/akismet/wrapper.php  
  inflating: wordpress/wp-content/plugins/akismet/class.akismet.php  
  inflating: wordpress/wp-content/plugins/akismet/akismet.php  
  inflating: wordpress/wp-content/plugins/akismet/class.akismet-widget.php  
  inflating: wordpress/wp-content/plugins/akismet/.htaccess  
  inflating: wordpress/wp-content/plugins/hello.php  
  inflating: wordpress/licencia.txt  
  inflating: wordpress/wp-blog-header.php  
  inflating: wordpress/wp-signup.php  
  inflating: wordpress/index.php     
  inflating: wordpress/license.txt   
  inflating: wordpress/wp-config-sample.php  
  inflating: wordpress/wp-load.php   
  inflating: wordpress/readme.html   
   creating: wordpress/wp-admin/
  inflating: wordpress/wp-admin/ms-edit.php  
  inflating: wordpress/wp-admin/ms-options.php  
  inflating: wordpress/wp-admin/admin-footer.php  
  inflating: wordpress/wp-admin/options-writing.php  
   creating: wordpress/wp-admin/includes/
  inflating: wordpress/wp-admin/includes/class-wp-plugins-list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-ajax-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/class-theme-installer-skin.php  
  inflating: wordpress/wp-admin/includes/class-file-upload-upgrader.php  
  inflating: wordpress/wp-admin/includes/class-core-upgrader.php  
  inflating: wordpress/wp-admin/includes/class-ftp-sockets.php  
  inflating: wordpress/wp-admin/includes/class-wp-ms-themes-list-table.php  
  inflating: wordpress/wp-admin/includes/class-automatic-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/upgrade.php  
  inflating: wordpress/wp-admin/includes/class-wp-filesystem-ftpext.php  
  inflating: wordpress/wp-admin/includes/class-wp-filesystem-ftpsockets.php  
  inflating: wordpress/wp-admin/includes/nav-menu.php  
  inflating: wordpress/wp-admin/includes/class-wp-internal-pointers.php  
  inflating: wordpress/wp-admin/includes/class-wp-theme-install-list-table.php  
  inflating: wordpress/wp-admin/includes/misc.php  
  inflating: wordpress/wp-admin/includes/class-pclzip.php  
  inflating: wordpress/wp-admin/includes/class-walker-category-checklist.php  
  inflating: wordpress/wp-admin/includes/class-wp-terms-list-table.php  
  inflating: wordpress/wp-admin/includes/theme-install.php  
  inflating: wordpress/wp-admin/includes/plugin-install.php  
  inflating: wordpress/wp-admin/includes/deprecated.php  
  inflating: wordpress/wp-admin/includes/revision.php  
  inflating: wordpress/wp-admin/includes/export.php  
  inflating: wordpress/wp-admin/includes/ms.php  
  inflating: wordpress/wp-admin/includes/class-bulk-theme-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/taxonomy.php  
  inflating: wordpress/wp-admin/includes/admin.php  
  inflating: wordpress/wp-admin/includes/class-wp-community-events.php  
  inflating: wordpress/wp-admin/includes/class-ftp-pure.php  
  inflating: wordpress/wp-admin/includes/class-wp-users-list-table.php  
  inflating: wordpress/wp-admin/includes/menu.php  
  inflating: wordpress/wp-admin/includes/schema.php  
  inflating: wordpress/wp-admin/includes/class-wp-upgrader.php  
  inflating: wordpress/wp-admin/includes/bookmark.php  
  inflating: wordpress/wp-admin/includes/class-wp-themes-list-table.php  
  inflating: wordpress/wp-admin/includes/options.php  
  inflating: wordpress/wp-admin/includes/class-wp-importer.php  
  inflating: wordpress/wp-admin/includes/list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-automatic-updater.php  
  inflating: wordpress/wp-admin/includes/class-theme-upgrader.php  
  inflating: wordpress/wp-admin/includes/dashboard.php  
  inflating: wordpress/wp-admin/includes/class-bulk-plugin-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/noop.php  
  inflating: wordpress/wp-admin/includes/class-wp-media-list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-ms-users-list-table.php  
  inflating: wordpress/wp-admin/includes/ms-admin-filters.php  
  inflating: wordpress/wp-admin/includes/class-walker-nav-menu-edit.php  
  inflating: wordpress/wp-admin/includes/class-wp-screen.php  
  inflating: wordpress/wp-admin/includes/update.php  
  inflating: wordpress/wp-admin/includes/class-wp-posts-list-table.php  
  inflating: wordpress/wp-admin/includes/file.php  
  inflating: wordpress/wp-admin/includes/credits.php  
  inflating: wordpress/wp-admin/includes/class-plugin-upgrader.php  
  inflating: wordpress/wp-admin/includes/class-wp-filesystem-base.php  
  inflating: wordpress/wp-admin/includes/admin-filters.php  
  inflating: wordpress/wp-admin/includes/image-edit.php  
  inflating: wordpress/wp-admin/includes/plugin.php  
  inflating: wordpress/wp-admin/includes/class-language-pack-upgrader.php  
  inflating: wordpress/wp-admin/includes/network.php  
  inflating: wordpress/wp-admin/includes/class-wp-filesystem-direct.php  
  inflating: wordpress/wp-admin/includes/image.php  
  inflating: wordpress/wp-admin/includes/widgets.php  
  inflating: wordpress/wp-admin/includes/import.php  
  inflating: wordpress/wp-admin/includes/continents-cities.php  
  inflating: wordpress/wp-admin/includes/edit-tag-messages.php  
  inflating: wordpress/wp-admin/includes/template.php  
  inflating: wordpress/wp-admin/includes/translation-install.php  
  inflating: wordpress/wp-admin/includes/class-ftp.php  
  inflating: wordpress/wp-admin/includes/screen.php  
  inflating: wordpress/wp-admin/includes/post.php  
  inflating: wordpress/wp-admin/includes/class-wp-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/ms-deprecated.php  
  inflating: wordpress/wp-admin/includes/update-core.php  
  inflating: wordpress/wp-admin/includes/class-plugin-installer-skin.php  
  inflating: wordpress/wp-admin/includes/comment.php  
  inflating: wordpress/wp-admin/includes/class-wp-list-table-compat.php  
  inflating: wordpress/wp-admin/includes/user.php  
  inflating: wordpress/wp-admin/includes/class-wp-comments-list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-plugin-install-list-table.php  
  inflating: wordpress/wp-admin/includes/theme.php  
  inflating: wordpress/wp-admin/includes/class-wp-site-icon.php  
  inflating: wordpress/wp-admin/includes/ajax-actions.php  
  inflating: wordpress/wp-admin/includes/class-theme-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/class-wp-links-list-table.php  
  inflating: wordpress/wp-admin/includes/class-language-pack-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/class-wp-ms-sites-list-table.php  
  inflating: wordpress/wp-admin/includes/class-wp-post-comments-list-table.php  
  inflating: wordpress/wp-admin/includes/media.php  
  inflating: wordpress/wp-admin/includes/class-walker-nav-menu-checklist.php  
  inflating: wordpress/wp-admin/includes/class-plugin-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/class-wp-filesystem-ssh2.php  
  inflating: wordpress/wp-admin/includes/meta-boxes.php  
  inflating: wordpress/wp-admin/includes/class-bulk-upgrader-skin.php  
  inflating: wordpress/wp-admin/includes/class-wp-upgrader-skins.php  
  inflating: wordpress/wp-admin/upgrade.php  
  inflating: wordpress/wp-admin/ms-upgrade-network.php  
  inflating: wordpress/wp-admin/tools.php  
  inflating: wordpress/wp-admin/ms-users.php  
  inflating: wordpress/wp-admin/menu-header.php  
  inflating: wordpress/wp-admin/moderation.php  
  inflating: wordpress/wp-admin/edit-form-advanced.php  
  inflating: wordpress/wp-admin/load-scripts.php  
  inflating: wordpress/wp-admin/theme-install.php  
  inflating: wordpress/wp-admin/plugin-install.php  
  inflating: wordpress/wp-admin/revision.php  
  inflating: wordpress/wp-admin/install-helper.php  
  inflating: wordpress/wp-admin/media-new.php  
  inflating: wordpress/wp-admin/export.php  
  inflating: wordpress/wp-admin/themes.php  
  inflating: wordpress/wp-admin/edit-tag-form.php  
  inflating: wordpress/wp-admin/press-this.php  
  inflating: wordpress/wp-admin/users.php  
  inflating: wordpress/wp-admin/ms-themes.php  
  inflating: wordpress/wp-admin/nav-menus.php  
  inflating: wordpress/wp-admin/link-add.php  
  inflating: wordpress/wp-admin/admin.php  
  inflating: wordpress/wp-admin/privacy.php  
  inflating: wordpress/wp-admin/my-sites.php  
  inflating: wordpress/wp-admin/plugins.php  
  inflating: wordpress/wp-admin/customize.php  
  inflating: wordpress/wp-admin/menu.php  
  inflating: wordpress/wp-admin/admin-header.php  
  inflating: wordpress/wp-admin/options.php  
  inflating: wordpress/wp-admin/options-permalink.php  
  inflating: wordpress/wp-admin/admin-ajax.php  
  inflating: wordpress/wp-admin/edit-comments.php  
   creating: wordpress/wp-admin/js/
  inflating: wordpress/wp-admin/js/theme-plugin-editor.min.js  
  inflating: wordpress/wp-admin/js/customize-nav-menus.js  
  inflating: wordpress/wp-admin/js/xfn.js  
  inflating: wordpress/wp-admin/js/customize-nav-menus.min.js  
  inflating: wordpress/wp-admin/js/updates.min.js  
  inflating: wordpress/wp-admin/js/word-count.min.js  
  inflating: wordpress/wp-admin/js/inline-edit-tax.min.js  
  inflating: wordpress/wp-admin/js/media-gallery.min.js  
  inflating: wordpress/wp-admin/js/editor.js  
  inflating: wordpress/wp-admin/js/edit-comments.min.js  
  inflating: wordpress/wp-admin/js/media-upload.js  
  inflating: wordpress/wp-admin/js/plugin-install.min.js  
  inflating: wordpress/wp-admin/js/customize-widgets.min.js  
  inflating: wordpress/wp-admin/js/theme-plugin-editor.js  
  inflating: wordpress/wp-admin/js/tags.js  
   creating: wordpress/wp-admin/js/widgets/
  inflating: wordpress/wp-admin/js/widgets/custom-html-widgets.js  
  inflating: wordpress/wp-admin/js/widgets/media-image-widget.js  
  inflating: wordpress/wp-admin/js/widgets/custom-html-widgets.min.js  
  inflating: wordpress/wp-admin/js/widgets/media-audio-widget.js  
  inflating: wordpress/wp-admin/js/widgets/media-widgets.min.js  
  inflating: wordpress/wp-admin/js/widgets/media-audio-widget.min.js  
  inflating: wordpress/wp-admin/js/widgets/media-widgets.js  
  inflating: wordpress/wp-admin/js/widgets/media-gallery-widget.min.js  
  inflating: wordpress/wp-admin/js/widgets/media-image-widget.min.js  
  inflating: wordpress/wp-admin/js/widgets/text-widgets.min.js  
  inflating: wordpress/wp-admin/js/widgets/text-widgets.js  
  inflating: wordpress/wp-admin/js/widgets/media-video-widget.js  
  inflating: wordpress/wp-admin/js/widgets/media-gallery-widget.js  
  inflating: wordpress/wp-admin/js/widgets/media-video-widget.min.js  
  inflating: wordpress/wp-admin/js/tags-suggest.js  
  inflating: wordpress/wp-admin/js/nav-menu.js  
  inflating: wordpress/wp-admin/js/widgets.js  
  inflating: wordpress/wp-admin/js/postbox.js  
  inflating: wordpress/wp-admin/js/media.min.js  
  inflating: wordpress/wp-admin/js/media.js  
  inflating: wordpress/wp-admin/js/iris.min.js  
  inflating: wordpress/wp-admin/js/user-profile.min.js  
  inflating: wordpress/wp-admin/js/svg-painter.js  
  inflating: wordpress/wp-admin/js/user-profile.js  
  inflating: wordpress/wp-admin/js/inline-edit-post.js  
  inflating: wordpress/wp-admin/js/postbox.min.js  
  inflating: wordpress/wp-admin/js/media-gallery.js  
  inflating: wordpress/wp-admin/js/user-suggest.min.js  
  inflating: wordpress/wp-admin/js/tags-box.min.js  
  inflating: wordpress/wp-admin/js/revisions.min.js  
  inflating: wordpress/wp-admin/js/customize-controls.min.js  
  inflating: wordpress/wp-admin/js/customize-controls.js  
  inflating: wordpress/wp-admin/js/post.js  
  inflating: wordpress/wp-admin/js/color-picker.min.js  
  inflating: wordpress/wp-admin/js/word-count.js  
  inflating: wordpress/wp-admin/js/xfn.min.js  
  inflating: wordpress/wp-admin/js/custom-background.js  
  inflating: wordpress/wp-admin/js/comment.js  
  inflating: wordpress/wp-admin/js/wp-fullscreen-stub.js  
  inflating: wordpress/wp-admin/js/common.min.js  
  inflating: wordpress/wp-admin/js/tags-suggest.min.js  
  inflating: wordpress/wp-admin/js/revisions.js  
  inflating: wordpress/wp-admin/js/updates.js  
  inflating: wordpress/wp-admin/js/inline-edit-post.min.js  
  inflating: wordpress/wp-admin/js/editor-expand.min.js  
  inflating: wordpress/wp-admin/js/image-edit.min.js  
  inflating: wordpress/wp-admin/js/tags-box.js  
  inflating: wordpress/wp-admin/js/svg-painter.min.js  
  inflating: wordpress/wp-admin/js/edit-comments.js  
  inflating: wordpress/wp-admin/js/custom-header.js  
  inflating: wordpress/wp-admin/js/comment.min.js  
  inflating: wordpress/wp-admin/js/post.min.js  
  inflating: wordpress/wp-admin/js/gallery.min.js  
  inflating: wordpress/wp-admin/js/inline-edit-tax.js  
  inflating: wordpress/wp-admin/js/custom-background.min.js  
  inflating: wordpress/wp-admin/js/code-editor.min.js  
  inflating: wordpress/wp-admin/js/theme.js  
  inflating: wordpress/wp-admin/js/tags.min.js  
  inflating: wordpress/wp-admin/js/set-post-thumbnail.min.js  
  inflating: wordpress/wp-admin/js/user-suggest.js  
  inflating: wordpress/wp-admin/js/dashboard.js  
  inflating: wordpress/wp-admin/js/dashboard.min.js  
  inflating: wordpress/wp-admin/js/plugin-install.js  
  inflating: wordpress/wp-admin/js/link.js  
  inflating: wordpress/wp-admin/js/color-picker.js  
  inflating: wordpress/wp-admin/js/media-upload.min.js  
  inflating: wordpress/wp-admin/js/accordion.min.js  
  inflating: wordpress/wp-admin/js/common.js  
  inflating: wordpress/wp-admin/js/password-strength-meter.min.js  
  inflating: wordpress/wp-admin/js/nav-menu.min.js  
  inflating: wordpress/wp-admin/js/image-edit.js  
  inflating: wordpress/wp-admin/js/language-chooser.js  
  inflating: wordpress/wp-admin/js/code-editor.js  
  inflating: wordpress/wp-admin/js/link.min.js  
  inflating: wordpress/wp-admin/js/widgets.min.js  
  inflating: wordpress/wp-admin/js/accordion.js  
  inflating: wordpress/wp-admin/js/editor.min.js  
  inflating: wordpress/wp-admin/js/set-post-thumbnail.js  
  inflating: wordpress/wp-admin/js/customize-widgets.js  
  inflating: wordpress/wp-admin/js/gallery.js  
  inflating: wordpress/wp-admin/js/farbtastic.js  
  inflating: wordpress/wp-admin/js/language-chooser.min.js  
  inflating: wordpress/wp-admin/js/editor-expand.js  
  inflating: wordpress/wp-admin/js/wp-fullscreen-stub.min.js  
  inflating: wordpress/wp-admin/js/theme.min.js  
  inflating: wordpress/wp-admin/js/password-strength-meter.js  
  inflating: wordpress/wp-admin/user-edit.php  
  inflating: wordpress/wp-admin/custom-header.php  
  inflating: wordpress/wp-admin/update.php  
  inflating: wordpress/wp-admin/about.php  
  inflating: wordpress/wp-admin/index.php  
  inflating: wordpress/wp-admin/credits.php  
  inflating: wordpress/wp-admin/link.php  
  inflating: wordpress/wp-admin/edit-link-form.php  
  inflating: wordpress/wp-admin/network.php  
  inflating: wordpress/wp-admin/options-general.php  
  inflating: wordpress/wp-admin/options-media.php  
   creating: wordpress/wp-admin/images/
  inflating: wordpress/wp-admin/images/align-left-2x.png  
  inflating: wordpress/wp-admin/images/arrows.png  
  inflating: wordpress/wp-admin/images/icons32.png  
  inflating: wordpress/wp-admin/images/menu-2x.png  
  inflating: wordpress/wp-admin/images/imgedit-icons-2x.png  
 extracting: wordpress/wp-admin/images/post-formats.png  
  inflating: wordpress/wp-admin/images/icons32-2x.png  
  inflating: wordpress/wp-admin/images/wordpress-logo.svg  
 extracting: wordpress/wp-admin/images/media-button-music.gif  
 extracting: wordpress/wp-admin/images/menu.png  
 extracting: wordpress/wp-admin/images/list-2x.png  
  inflating: wordpress/wp-admin/images/resize.gif  
 extracting: wordpress/wp-admin/images/date-button.gif  
  inflating: wordpress/wp-admin/images/wordpress-logo.png  
 extracting: wordpress/wp-admin/images/align-right.png  
  inflating: wordpress/wp-admin/images/align-none-2x.png  
  inflating: wordpress/wp-admin/images/bubble_bg.gif  
 extracting: wordpress/wp-admin/images/list.png  
  inflating: wordpress/wp-admin/images/wpspin_light-2x.gif  
 extracting: wordpress/wp-admin/images/menu-vs.png  
  inflating: wordpress/wp-admin/images/align-right-2x.png  
  inflating: wordpress/wp-admin/images/browser-rtl.png  
  inflating: wordpress/wp-admin/images/menu-vs-2x.png  
 extracting: wordpress/wp-admin/images/media-button-other.gif  
  inflating: wordpress/wp-admin/images/align-center-2x.png  
  inflating: wordpress/wp-admin/images/xit-2x.gif  
  inflating: wordpress/wp-admin/images/arrows-2x.png  
  inflating: wordpress/wp-admin/images/spinner-2x.gif  
 extracting: wordpress/wp-admin/images/align-left.png  
  inflating: wordpress/wp-admin/images/se.png  
  inflating: wordpress/wp-admin/images/sort-2x.gif  
  inflating: wordpress/wp-admin/images/w-logo-blue.png  
  inflating: wordpress/wp-admin/images/resize-rtl.gif  
  inflating: wordpress/wp-admin/images/loading.gif  
  inflating: wordpress/wp-admin/images/sort.gif  
  inflating: wordpress/wp-admin/images/imgedit-icons.png  
 extracting: wordpress/wp-admin/images/yes.png  
  inflating: wordpress/wp-admin/images/media-button-image.gif  
  inflating: wordpress/wp-admin/images/post-formats-vs.png  
 extracting: wordpress/wp-admin/images/align-none.png  
 extracting: wordpress/wp-admin/images/mask.png  
 extracting: wordpress/wp-admin/images/stars.png  
 extracting: wordpress/wp-admin/images/marker.png  
  inflating: wordpress/wp-admin/images/post-formats32-vs.png  
 extracting: wordpress/wp-admin/images/bubble_bg-2x.gif  
 extracting: wordpress/wp-admin/images/media-button-video.gif  
 extracting: wordpress/wp-admin/images/stars-2x.png  
  inflating: wordpress/wp-admin/images/comment-grey-bubble.png  
  inflating: wordpress/wp-admin/images/no.png  
 extracting: wordpress/wp-admin/images/resize-2x.gif  
  inflating: wordpress/wp-admin/images/browser.png  
 extracting: wordpress/wp-admin/images/comment-grey-bubble-2x.png  
 extracting: wordpress/wp-admin/images/generic.png  
  inflating: wordpress/wp-admin/images/spinner.gif  
  inflating: wordpress/wp-admin/images/date-button-2x.gif  
  inflating: wordpress/wp-admin/images/icons32-vs.png  
 extracting: wordpress/wp-admin/images/media-button.png  
  inflating: wordpress/wp-admin/images/wordpress-logo-white.svg  
 extracting: wordpress/wp-admin/images/align-center.png  
  inflating: wordpress/wp-admin/images/wpspin_light.gif  
 extracting: wordpress/wp-admin/images/media-button-2x.png  
  inflating: wordpress/wp-admin/images/icons32-vs-2x.png  
  inflating: wordpress/wp-admin/images/w-logo-white.png  
 extracting: wordpress/wp-admin/images/xit.gif  
  inflating: wordpress/wp-admin/images/post-formats32.png  
  inflating: wordpress/wp-admin/images/wheel.png  
 extracting: wordpress/wp-admin/images/resize-rtl-2x.gif  
  inflating: wordpress/wp-admin/theme-editor.php  
   creating: wordpress/wp-admin/user/
  inflating: wordpress/wp-admin/user/admin.php  
  inflating: wordpress/wp-admin/user/privacy.php  
  inflating: wordpress/wp-admin/user/menu.php  
  inflating: wordpress/wp-admin/user/user-edit.php  
  inflating: wordpress/wp-admin/user/about.php  
  inflating: wordpress/wp-admin/user/index.php  
  inflating: wordpress/wp-admin/user/credits.php  
  inflating: wordpress/wp-admin/user/freedoms.php  
  inflating: wordpress/wp-admin/user/profile.php  
  inflating: wordpress/wp-admin/widgets.php  
  inflating: wordpress/wp-admin/import.php  
  inflating: wordpress/wp-admin/ms-sites.php  
  inflating: wordpress/wp-admin/ms-admin.php  
  inflating: wordpress/wp-admin/upgrade-functions.php  
  inflating: wordpress/wp-admin/freedoms.php  
  inflating: wordpress/wp-admin/media-upload.php  
  inflating: wordpress/wp-admin/plugin-editor.php  
  inflating: wordpress/wp-admin/async-upload.php  
  inflating: wordpress/wp-admin/post.php  
   creating: wordpress/wp-admin/network/
  inflating: wordpress/wp-admin/network/site-info.php  
  inflating: wordpress/wp-admin/network/upgrade.php  
  inflating: wordpress/wp-admin/network/setup.php  
  inflating: wordpress/wp-admin/network/theme-install.php  
  inflating: wordpress/wp-admin/network/plugin-install.php  
  inflating: wordpress/wp-admin/network/themes.php  
  inflating: wordpress/wp-admin/network/users.php  
  inflating: wordpress/wp-admin/network/admin.php  
  inflating: wordpress/wp-admin/network/privacy.php  
  inflating: wordpress/wp-admin/network/plugins.php  
  inflating: wordpress/wp-admin/network/site-settings.php  
  inflating: wordpress/wp-admin/network/menu.php  
  inflating: wordpress/wp-admin/network/site-themes.php  
  inflating: wordpress/wp-admin/network/user-edit.php  
  inflating: wordpress/wp-admin/network/settings.php  
  inflating: wordpress/wp-admin/network/update.php  
  inflating: wordpress/wp-admin/network/about.php  
  inflating: wordpress/wp-admin/network/index.php  
  inflating: wordpress/wp-admin/network/credits.php  
  inflating: wordpress/wp-admin/network/theme-editor.php  
  inflating: wordpress/wp-admin/network/site-users.php  
  inflating: wordpress/wp-admin/network/freedoms.php  
  inflating: wordpress/wp-admin/network/plugin-editor.php  
  inflating: wordpress/wp-admin/network/update-core.php  
  inflating: wordpress/wp-admin/network/profile.php  
  inflating: wordpress/wp-admin/network/sites.php  
  inflating: wordpress/wp-admin/network/user-new.php  
  inflating: wordpress/wp-admin/network/edit.php  
  inflating: wordpress/wp-admin/network/site-new.php  
  inflating: wordpress/wp-admin/link-manager.php  
  inflating: wordpress/wp-admin/update-core.php  
  inflating: wordpress/wp-admin/profile.php  
  inflating: wordpress/wp-admin/setup-config.php  
  inflating: wordpress/wp-admin/ms-delete-site.php  
  inflating: wordpress/wp-admin/comment.php  
  inflating: wordpress/wp-admin/term.php  
  inflating: wordpress/wp-admin/load-styles.php  
  inflating: wordpress/wp-admin/user-new.php  
  inflating: wordpress/wp-admin/post-new.php  
  inflating: wordpress/wp-admin/admin-functions.php  
   creating: wordpress/wp-admin/maint/
  inflating: wordpress/wp-admin/maint/repair.php  
  inflating: wordpress/wp-admin/options-reading.php  
  inflating: wordpress/wp-admin/options-head.php  
  inflating: wordpress/wp-admin/link-parse-opml.php  
  inflating: wordpress/wp-admin/custom-background.php  
  inflating: wordpress/wp-admin/options-discussion.php  
  inflating: wordpress/wp-admin/edit.php  
  inflating: wordpress/wp-admin/media.php  
  inflating: wordpress/wp-admin/edit-form-comment.php  
  inflating: wordpress/wp-admin/upload.php  
  inflating: wordpress/wp-admin/install.php  
  inflating: wordpress/wp-admin/admin-post.php  
  inflating: wordpress/wp-admin/edit-tags.php  
   creating: wordpress/wp-admin/css/
  inflating: wordpress/wp-admin/css/customize-controls.css  
  inflating: wordpress/wp-admin/css/customize-controls-rtl.css  
  inflating: wordpress/wp-admin/css/about.css  
  inflating: wordpress/wp-admin/css/themes.min.css  
  inflating: wordpress/wp-admin/css/admin-menu-rtl.min.css  
  inflating: wordpress/wp-admin/css/deprecated-media.css  
  inflating: wordpress/wp-admin/css/admin-menu.min.css  
  inflating: wordpress/wp-admin/css/deprecated-media-rtl.css  
  inflating: wordpress/wp-admin/css/customize-nav-menus-rtl.css  
  inflating: wordpress/wp-admin/css/dashboard.css  
  inflating: wordpress/wp-admin/css/code-editor.min.css  
  inflating: wordpress/wp-admin/css/common.min.css  
  inflating: wordpress/wp-admin/css/revisions-rtl.min.css  
  inflating: wordpress/wp-admin/css/widgets-rtl.css  
  inflating: wordpress/wp-admin/css/farbtastic-rtl.min.css  
  inflating: wordpress/wp-admin/css/revisions.css  
  inflating: wordpress/wp-admin/css/customize-nav-menus-rtl.min.css  
  inflating: wordpress/wp-admin/css/customize-widgets-rtl.min.css  
  inflating: wordpress/wp-admin/css/code-editor.css  
  inflating: wordpress/wp-admin/css/media.min.css  
  inflating: wordpress/wp-admin/css/common-rtl.css  
  inflating: wordpress/wp-admin/css/farbtastic.css  
  inflating: wordpress/wp-admin/css/customize-widgets.css  
  inflating: wordpress/wp-admin/css/media-rtl.css  
  inflating: wordpress/wp-admin/css/about-rtl.css  
  inflating: wordpress/wp-admin/css/edit-rtl.min.css  
  inflating: wordpress/wp-admin/css/wp-admin-rtl.min.css  
  inflating: wordpress/wp-admin/css/farbtastic-rtl.css  
  inflating: wordpress/wp-admin/css/farbtastic.min.css  
  inflating: wordpress/wp-admin/css/edit.css  
  inflating: wordpress/wp-admin/css/wp-admin.min.css  
  inflating: wordpress/wp-admin/css/l10n-rtl.min.css  
  inflating: wordpress/wp-admin/css/revisions.min.css  
  inflating: wordpress/wp-admin/css/nav-menus-rtl.min.css  
  inflating: wordpress/wp-admin/css/forms.min.css  
  inflating: wordpress/wp-admin/css/login-rtl.min.css  
  inflating: wordpress/wp-admin/css/login.css  
  inflating: wordpress/wp-admin/css/customize-controls.min.css  
  inflating: wordpress/wp-admin/css/wp-admin-rtl.css  
  inflating: wordpress/wp-admin/css/dashboard-rtl.min.css  
  inflating: wordpress/wp-admin/css/customize-nav-menus.css  
  inflating: wordpress/wp-admin/css/edit.min.css  
  inflating: wordpress/wp-admin/css/code-editor-rtl.css  
  inflating: wordpress/wp-admin/css/list-tables.min.css  
  inflating: wordpress/wp-admin/css/forms.css  
  inflating: wordpress/wp-admin/css/nav-menus.min.css  
  inflating: wordpress/wp-admin/css/ie.css  
  inflating: wordpress/wp-admin/css/wp-admin.css  
  inflating: wordpress/wp-admin/css/code-editor-rtl.min.css  
  inflating: wordpress/wp-admin/css/about-rtl.min.css  
  inflating: wordpress/wp-admin/css/deprecated-media-rtl.min.css  
  inflating: wordpress/wp-admin/css/nav-menus-rtl.css  
  inflating: wordpress/wp-admin/css/forms-rtl.css  
  inflating: wordpress/wp-admin/css/themes-rtl.min.css  
  inflating: wordpress/wp-admin/css/forms-rtl.min.css  
  inflating: wordpress/wp-admin/css/widgets.css  
  inflating: wordpress/wp-admin/css/login-rtl.css  
  inflating: wordpress/wp-admin/css/site-icon.css  
  inflating: wordpress/wp-admin/css/widgets.min.css  
  inflating: wordpress/wp-admin/css/site-icon.min.css  
  inflating: wordpress/wp-admin/css/widgets-rtl.min.css  
  inflating: wordpress/wp-admin/css/list-tables-rtl.min.css  
  inflating: wordpress/wp-admin/css/color-picker.css  
  inflating: wordpress/wp-admin/css/customize-widgets.min.css  
  inflating: wordpress/wp-admin/css/media.css  
  inflating: wordpress/wp-admin/css/customize-nav-menus.min.css  
  inflating: wordpress/wp-admin/css/customize-widgets-rtl.css  
  inflating: wordpress/wp-admin/css/install-rtl.min.css  
  inflating: wordpress/wp-admin/css/admin-menu.css  
  inflating: wordpress/wp-admin/css/l10n-rtl.css  
  inflating: wordpress/wp-admin/css/edit-rtl.css  
  inflating: wordpress/wp-admin/css/common-rtl.min.css  
  inflating: wordpress/wp-admin/css/color-picker-rtl.min.css  
  inflating: wordpress/wp-admin/css/site-icon-rtl.css  
  inflating: wordpress/wp-admin/css/install.min.css  
  inflating: wordpress/wp-admin/css/media-rtl.min.css  
  inflating: wordpress/wp-admin/css/themes.css  
  inflating: wordpress/wp-admin/css/common.css  
  inflating: wordpress/wp-admin/css/admin-menu-rtl.css  
  inflating: wordpress/wp-admin/css/color-picker-rtl.css  
  inflating: wordpress/wp-admin/css/list-tables.css  
   creating: wordpress/wp-admin/css/colors/
   creating: wordpress/wp-admin/css/colors/blue/
  inflating: wordpress/wp-admin/css/colors/blue/colors.css  
  inflating: wordpress/wp-admin/css/colors/blue/colors.scss  
  inflating: wordpress/wp-admin/css/colors/blue/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/blue/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/blue/colors-rtl.min.css  
   creating: wordpress/wp-admin/css/colors/ocean/
  inflating: wordpress/wp-admin/css/colors/ocean/colors.css  
  inflating: wordpress/wp-admin/css/colors/ocean/colors.scss  
  inflating: wordpress/wp-admin/css/colors/ocean/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/ocean/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/ocean/colors-rtl.min.css  
  inflating: wordpress/wp-admin/css/colors/_variables.scss  
   creating: wordpress/wp-admin/css/colors/midnight/
  inflating: wordpress/wp-admin/css/colors/midnight/colors.css  
  inflating: wordpress/wp-admin/css/colors/midnight/colors.scss  
  inflating: wordpress/wp-admin/css/colors/midnight/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/midnight/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/midnight/colors-rtl.min.css  
  inflating: wordpress/wp-admin/css/colors/_mixins.scss  
   creating: wordpress/wp-admin/css/colors/ectoplasm/
  inflating: wordpress/wp-admin/css/colors/ectoplasm/colors.css  
  inflating: wordpress/wp-admin/css/colors/ectoplasm/colors.scss  
  inflating: wordpress/wp-admin/css/colors/ectoplasm/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/ectoplasm/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/ectoplasm/colors-rtl.min.css  
   creating: wordpress/wp-admin/css/colors/light/
  inflating: wordpress/wp-admin/css/colors/light/colors.css  
  inflating: wordpress/wp-admin/css/colors/light/colors.scss  
  inflating: wordpress/wp-admin/css/colors/light/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/light/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/light/colors-rtl.min.css  
  inflating: wordpress/wp-admin/css/colors/_admin.scss  
   creating: wordpress/wp-admin/css/colors/coffee/
  inflating: wordpress/wp-admin/css/colors/coffee/colors.css  
  inflating: wordpress/wp-admin/css/colors/coffee/colors.scss  
  inflating: wordpress/wp-admin/css/colors/coffee/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/coffee/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/coffee/colors-rtl.min.css  
   creating: wordpress/wp-admin/css/colors/sunrise/
  inflating: wordpress/wp-admin/css/colors/sunrise/colors.css  
  inflating: wordpress/wp-admin/css/colors/sunrise/colors.scss  
  inflating: wordpress/wp-admin/css/colors/sunrise/colors-rtl.css  
  inflating: wordpress/wp-admin/css/colors/sunrise/colors.min.css  
  inflating: wordpress/wp-admin/css/colors/sunrise/colors-rtl.min.css  
  inflating: wordpress/wp-admin/css/install-rtl.css  
  inflating: wordpress/wp-admin/css/color-picker.min.css  
  inflating: wordpress/wp-admin/css/about.min.css  
  inflating: wordpress/wp-admin/css/site-icon-rtl.min.css  
  inflating: wordpress/wp-admin/css/l10n.css  
  inflating: wordpress/wp-admin/css/revisions-rtl.css  
  inflating: wordpress/wp-admin/css/login.min.css  
  inflating: wordpress/wp-admin/css/ie-rtl.min.css  
  inflating: wordpress/wp-admin/css/customize-controls-rtl.min.css  
  inflating: wordpress/wp-admin/css/dashboard.min.css  
  inflating: wordpress/wp-admin/css/themes-rtl.css  
  inflating: wordpress/wp-admin/css/dashboard-rtl.css  
  inflating: wordpress/wp-admin/css/install.css  
  inflating: wordpress/wp-admin/css/deprecated-media.min.css  
  inflating: wordpress/wp-admin/css/ie-rtl.css  
  inflating: wordpress/wp-admin/css/list-tables-rtl.css  
  inflating: wordpress/wp-admin/css/nav-menus.css  
  inflating: wordpress/wp-admin/css/l10n.min.css  
  inflating: wordpress/wp-admin/css/ie.min.css  
  inflating: wordpress/wp-login.php  
  inflating: wordpress/wp-settings.php  
  inflating: wordpress/wp-comments-post.php  
  inflating: wordpress/wp-links-opml.php  
   creating: wordpress/wp-includes/
  inflating: wordpress/wp-includes/class-wp-post.php  
  inflating: wordpress/wp-includes/class-wp-hook.php  
  inflating: wordpress/wp-includes/class-wp-customize-manager.php  
  inflating: wordpress/wp-includes/class-walker-comment.php  
  inflating: wordpress/wp-includes/class-wp-rewrite.php  
  inflating: wordpress/wp-includes/spl-autoload-compat.php  
  inflating: wordpress/wp-includes/post-thumbnail-template.php  
  inflating: wordpress/wp-includes/class-wp-image-editor.php  
   creating: wordpress/wp-includes/customize/
  inflating: wordpress/wp-includes/customize/class-wp-customize-code-editor-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-sidebar-section.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menus-panel.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-locations-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-widget-area-customize-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-section.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-header-image-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-header-image-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-custom-css-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-upload-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-cropped-image-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-image-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-themes-panel.php  
  inflating: wordpress/wp-includes/customize/class-wp-widget-form-customize-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-item-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-auto-add-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-color-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-partial.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-site-icon-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-themes-section.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-media-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-selective-refresh.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-name-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-background-position-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-new-menu-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-background-image-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-background-image-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-theme-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-item-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-filter-setting.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-nav-menu-location-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-date-time-control.php  
  inflating: wordpress/wp-includes/customize/class-wp-customize-new-menu-section.php  
  inflating: wordpress/wp-includes/class-wp-roles.php  
   creating: wordpress/wp-includes/IXR/
  inflating: wordpress/wp-includes/IXR/class-IXR-server.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-error.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-message.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-clientmulticall.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-introspectionserver.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-date.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-value.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-base64.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-client.php  
  inflating: wordpress/wp-includes/IXR/class-IXR-request.php  
  inflating: wordpress/wp-includes/ms-default-constants.php  
  inflating: wordpress/wp-includes/class-walker-category-dropdown.php  
  inflating: wordpress/wp-includes/nav-menu-template.php  
  inflating: wordpress/wp-includes/default-constants.php  
  inflating: wordpress/wp-includes/rss.php  
  inflating: wordpress/wp-includes/class-smtp.php  
  inflating: wordpress/wp-includes/bookmark-template.php  
  inflating: wordpress/wp-includes/load.php  
  inflating: wordpress/wp-includes/class-wp-network-query.php  
  inflating: wordpress/wp-includes/author-template.php  
  inflating: wordpress/wp-includes/class-json.php  
  inflating: wordpress/wp-includes/nav-menu.php  
  inflating: wordpress/wp-includes/class-wp-taxonomy.php  
  inflating: wordpress/wp-includes/class-wp-comment.php  
  inflating: wordpress/wp-includes/class-wp-tax-query.php  
  inflating: wordpress/wp-includes/embed-template.php  
  inflating: wordpress/wp-includes/class-wp-widget.php  
  inflating: wordpress/wp-includes/class-wp-session-tokens.php  
  inflating: wordpress/wp-includes/class-wp-customize-section.php  
  inflating: wordpress/wp-includes/class-wp-user-query.php  
  inflating: wordpress/wp-includes/class-wp-customize-setting.php  
  inflating: wordpress/wp-includes/class-wp-feed-cache.php  
  inflating: wordpress/wp-includes/feed-atom.php  
  inflating: wordpress/wp-includes/deprecated.php  
  inflating: wordpress/wp-includes/comment-template.php  
  inflating: wordpress/wp-includes/class-wp.php  
  inflating: wordpress/wp-includes/revision.php  
   creating: wordpress/wp-includes/rest-api/
  inflating: wordpress/wp-includes/rest-api/class-wp-rest-request.php  
   creating: wordpress/wp-includes/rest-api/endpoints/
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-settings-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-taxonomies-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-post-statuses-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-post-types-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php  
  inflating: wordpress/wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php  
  inflating: wordpress/wp-includes/rest-api/class-wp-rest-response.php  
  inflating: wordpress/wp-includes/rest-api/class-wp-rest-server.php  
   creating: wordpress/wp-includes/rest-api/fields/
  inflating: wordpress/wp-includes/rest-api/fields/class-wp-rest-user-meta-fields.php  
  inflating: wordpress/wp-includes/rest-api/fields/class-wp-rest-comment-meta-fields.php  
  inflating: wordpress/wp-includes/rest-api/fields/class-wp-rest-meta-fields.php  
  inflating: wordpress/wp-includes/rest-api/fields/class-wp-rest-term-meta-fields.php  
  inflating: wordpress/wp-includes/rest-api/fields/class-wp-rest-post-meta-fields.php  
   creating: wordpress/wp-includes/widgets/
  inflating: wordpress/wp-includes/widgets/class-wp-widget-media-video.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-tag-cloud.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-media.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-recent-comments.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-media-gallery.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-meta.php  
  inflating: wordpress/wp-includes/widgets/class-wp-nav-menu-widget.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-search.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-media-audio.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-categories.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-links.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-rss.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-custom-html.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-calendar.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-pages.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-archives.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-media-image.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-recent-posts.php  
  inflating: wordpress/wp-includes/widgets/class-wp-widget-text.php  
  inflating: wordpress/wp-includes/class-wp-simplepie-sanitize-kses.php  
  inflating: wordpress/wp-includes/default-widgets.php  
  inflating: wordpress/wp-includes/taxonomy.php  
  inflating: wordpress/wp-includes/cron.php  
   creating: wordpress/wp-includes/pomo/
  inflating: wordpress/wp-includes/pomo/po.php  
  inflating: wordpress/wp-includes/pomo/entry.php  
  inflating: wordpress/wp-includes/pomo/mo.php  
  inflating: wordpress/wp-includes/pomo/streams.php  
  inflating: wordpress/wp-includes/pomo/plural-forms.php  
  inflating: wordpress/wp-includes/pomo/translations.php  
  inflating: wordpress/wp-includes/query.php  
  inflating: wordpress/wp-includes/class-wp-comment-query.php  
  inflating: wordpress/wp-includes/class-wp-theme.php  
  inflating: wordpress/wp-includes/class-feed.php  
  inflating: wordpress/wp-includes/version.php  
  inflating: wordpress/wp-includes/atomlib.php  
  inflating: wordpress/wp-includes/feed-rdf.php  
  inflating: wordpress/wp-includes/template-loader.php  
  inflating: wordpress/wp-includes/class-wp-text-diff-renderer-inline.php  
  inflating: wordpress/wp-includes/bookmark.php  
   creating: wordpress/wp-includes/fonts/
  inflating: wordpress/wp-includes/fonts/dashicons.svg  
  inflating: wordpress/wp-includes/fonts/dashicons.eot  
  inflating: wordpress/wp-includes/fonts/dashicons.woff  
  inflating: wordpress/wp-includes/fonts/dashicons.ttf  
  inflating: wordpress/wp-includes/class-wp-customize-panel.php  
  inflating: wordpress/wp-includes/session.php  
  inflating: wordpress/wp-includes/capabilities.php  
  inflating: wordpress/wp-includes/category.php  
  inflating: wordpress/wp-includes/class-wp-widget-factory.php  
  inflating: wordpress/wp-includes/class-wp-http-cookie.php  
  inflating: wordpress/wp-includes/class-wp-customize-nav-menus.php  
  inflating: wordpress/wp-includes/class-oembed.php  
  inflating: wordpress/wp-includes/wp-diff.php  
  inflating: wordpress/wp-includes/feed.php  
  inflating: wordpress/wp-includes/registration.php  
   creating: wordpress/wp-includes/certificates/
  inflating: wordpress/wp-includes/certificates/ca-bundle.crt  
  inflating: wordpress/wp-includes/option.php  
   creating: wordpress/wp-includes/js/
  inflating: wordpress/wp-includes/js/zxcvbn-async.js  
   creating: wordpress/wp-includes/js/crop/
  inflating: wordpress/wp-includes/js/crop/marqueeHoriz.gif  
  inflating: wordpress/wp-includes/js/crop/marqueeVert.gif  
  inflating: wordpress/wp-includes/js/crop/cropper.js  
  inflating: wordpress/wp-includes/js/crop/cropper.css  
  inflating: wordpress/wp-includes/js/wpdialog.min.js  
  inflating: wordpress/wp-includes/js/wp-list-revisions.min.js  
   creating: wordpress/wp-includes/js/codemirror/
  inflating: wordpress/wp-includes/js/codemirror/jsonlint.js  
  inflating: wordpress/wp-includes/js/codemirror/csslint.js  
  inflating: wordpress/wp-includes/js/codemirror/jshint.js  
  inflating: wordpress/wp-includes/js/codemirror/codemirror.min.js  
  inflating: wordpress/wp-includes/js/codemirror/htmlhint.js  
  inflating: wordpress/wp-includes/js/codemirror/htmlhint-kses.js  
  inflating: wordpress/wp-includes/js/codemirror/codemirror.min.css  
  inflating: wordpress/wp-includes/js/wp-a11y.js  
  inflating: wordpress/wp-includes/js/wp-embed-template.min.js  
  inflating: wordpress/wp-includes/js/comment-reply.js  
  inflating: wordpress/wp-includes/js/comment-reply.min.js  
  inflating: wordpress/wp-includes/js/swfobject.js  
  inflating: wordpress/wp-includes/js/utils.min.js  
   creating: wordpress/wp-includes/js/jcrop/
  inflating: wordpress/wp-includes/js/jcrop/jquery.Jcrop.min.css  
  inflating: wordpress/wp-includes/js/jcrop/Jcrop.gif  
  inflating: wordpress/wp-includes/js/jcrop/jquery.Jcrop.min.js  
  inflating: wordpress/wp-includes/js/wplink.min.js  
   creating: wordpress/wp-includes/js/mediaelement/
  inflating: wordpress/wp-includes/js/mediaelement/mejs-controls.png  
   creating: wordpress/wp-includes/js/mediaelement/lang/
  inflating: wordpress/wp-includes/js/mediaelement/lang/pl.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/hu.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/de.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/ru.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/ro.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/ca.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/nl.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/fa.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/ja.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/sk.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/cs.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/it.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/ko.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/es.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/uk.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/zh.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/fr.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/zh-cn.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/pt.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/sv.js  
  inflating: wordpress/wp-includes/js/mediaelement/lang/hr.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelementplayer.css  
  inflating: wordpress/wp-includes/js/mediaelement/wp-mediaelement.css  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-migrate.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelementplayer-legacy.css  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-flash-video-hls.swf  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-and-player.js  
  inflating: wordpress/wp-includes/js/mediaelement/wp-mediaelement.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-flash-audio-ogg.swf  
  inflating: wordpress/wp-includes/js/mediaelement/wp-playlist.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement.js  
  inflating: wordpress/wp-includes/js/mediaelement/wp-playlist.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-flash-video-mdash.swf  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-migrate.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/wp-mediaelement.min.css  
   creating: wordpress/wp-includes/js/mediaelement/renderers/
  inflating: wordpress/wp-includes/js/mediaelement/renderers/vimeo.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/facebook.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/soundcloud.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/vimeo.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/soundcloud.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/twitch.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/facebook.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/dailymotion.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/dailymotion.min.js  
  inflating: wordpress/wp-includes/js/mediaelement/renderers/twitch.js  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelementplayer-legacy.min.css  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelementplayer.min.css  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement.min.js  
 extracting: wordpress/wp-includes/js/mediaelement/mediaelement-flash-video.swf  
 extracting: wordpress/wp-includes/js/mediaelement/mediaelement-flash-audio.swf  
  inflating: wordpress/wp-includes/js/mediaelement/wp-mediaelement.js  
  inflating: wordpress/wp-includes/js/mediaelement/mejs-controls.svg  
  inflating: wordpress/wp-includes/js/mediaelement/mediaelement-and-player.min.js  
  inflating: wordpress/wp-includes/js/imagesloaded.min.js  
   creating: wordpress/wp-includes/js/imgareaselect/
  inflating: wordpress/wp-includes/js/imgareaselect/jquery.imgareaselect.min.js  
  inflating: wordpress/wp-includes/js/imgareaselect/border-anim-v.gif  
  inflating: wordpress/wp-includes/js/imgareaselect/jquery.imgareaselect.js  
  inflating: wordpress/wp-includes/js/imgareaselect/border-anim-h.gif  
  inflating: wordpress/wp-includes/js/imgareaselect/imgareaselect.css  
   creating: wordpress/wp-includes/js/tinymce/
  inflating: wordpress/wp-includes/js/tinymce/tinymce.min.js  
   creating: wordpress/wp-includes/js/tinymce/utils/
  inflating: wordpress/wp-includes/js/tinymce/utils/form_utils.js  
  inflating: wordpress/wp-includes/js/tinymce/utils/mctabs.js  
  inflating: wordpress/wp-includes/js/tinymce/utils/validate.js  
  inflating: wordpress/wp-includes/js/tinymce/utils/editable_selects.js  
  inflating: wordpress/wp-includes/js/tinymce/wp-tinymce.js.gz  
  inflating: wordpress/wp-includes/js/tinymce/wp-tinymce.php  
  inflating: wordpress/wp-includes/js/tinymce/license.txt  
   creating: wordpress/wp-includes/js/tinymce/skins/
   creating: wordpress/wp-includes/js/tinymce/skins/wordpress/
   creating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/more.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/playlist-video.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/video.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/embedded.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/dashicon-no.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/dashicon-edit.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/audio.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/pagebreak.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/gallery.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/more-2x.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/images/gallery-2x.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/pagebreak-2x.png  
 extracting: wordpress/wp-includes/js/tinymce/skins/wordpress/images/playlist-audio.png  
  inflating: wordpress/wp-includes/js/tinymce/skins/wordpress/wp-content.css  
   creating: wordpress/wp-includes/js/tinymce/skins/lightgray/
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/content.min.css  
   creating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce.eot  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce.svg  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce-small.svg  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce-small.woff  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce.ttf  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce.woff  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce-small.ttf  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/fonts/tinymce-small.eot  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/skin.min.css  
   creating: wordpress/wp-includes/js/tinymce/skins/lightgray/img/
 extracting: wordpress/wp-includes/js/tinymce/skins/lightgray/img/object.gif  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/img/anchor.gif  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/img/trans.gif  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/img/loader.gif  
  inflating: wordpress/wp-includes/js/tinymce/skins/lightgray/content.inline.min.css  
   creating: wordpress/wp-includes/js/tinymce/langs/
  inflating: wordpress/wp-includes/js/tinymce/langs/wp-langs-en.js  
   creating: wordpress/wp-includes/js/tinymce/themes/
   creating: wordpress/wp-includes/js/tinymce/themes/inlite/
  inflating: wordpress/wp-includes/js/tinymce/themes/inlite/theme.js  
  inflating: wordpress/wp-includes/js/tinymce/themes/inlite/theme.min.js  
   creating: wordpress/wp-includes/js/tinymce/themes/modern/
  inflating: wordpress/wp-includes/js/tinymce/themes/modern/theme.js  
  inflating: wordpress/wp-includes/js/tinymce/themes/modern/theme.min.js  
  inflating: wordpress/wp-includes/js/tinymce/tiny_mce_popup.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/
   creating: wordpress/wp-includes/js/tinymce/plugins/wpdialogs/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpdialogs/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpdialogs/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wpautoresize/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpautoresize/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpautoresize/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/directionality/
  inflating: wordpress/wp-includes/js/tinymce/plugins/directionality/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/directionality/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/charmap/
  inflating: wordpress/wp-includes/js/tinymce/plugins/charmap/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/charmap/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/media/
  inflating: wordpress/wp-includes/js/tinymce/plugins/media/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/media/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/paste/
  inflating: wordpress/wp-includes/js/tinymce/plugins/paste/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/paste/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/image/
  inflating: wordpress/wp-includes/js/tinymce/plugins/image/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/image/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wptextpattern/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wptextpattern/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wptextpattern/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/textcolor/
  inflating: wordpress/wp-includes/js/tinymce/plugins/textcolor/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/textcolor/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/colorpicker/
  inflating: wordpress/wp-includes/js/tinymce/plugins/colorpicker/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/colorpicker/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/link/
  inflating: wordpress/wp-includes/js/tinymce/plugins/link/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/link/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wordpress/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wordpress/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wordpress/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/hr/
  inflating: wordpress/wp-includes/js/tinymce/plugins/hr/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/hr/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wpgallery/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpgallery/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpgallery/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/fullscreen/
  inflating: wordpress/wp-includes/js/tinymce/plugins/fullscreen/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/fullscreen/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wplink/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wplink/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wplink/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wpemoji/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpemoji/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpemoji/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wpeditimage/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpeditimage/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpeditimage/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/compat3x/
  inflating: wordpress/wp-includes/js/tinymce/plugins/compat3x/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/compat3x/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/compat3x/css/
  inflating: wordpress/wp-includes/js/tinymce/plugins/compat3x/css/dialog.css  
   creating: wordpress/wp-includes/js/tinymce/plugins/tabfocus/
  inflating: wordpress/wp-includes/js/tinymce/plugins/tabfocus/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/tabfocus/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/lists/
  inflating: wordpress/wp-includes/js/tinymce/plugins/lists/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/lists/plugin.min.js  
   creating: wordpress/wp-includes/js/tinymce/plugins/wpview/
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpview/plugin.js  
  inflating: wordpress/wp-includes/js/tinymce/plugins/wpview/plugin.min.js  
  inflating: wordpress/wp-includes/js/customize-preview-widgets.js  
  inflating: wordpress/wp-includes/js/wp-emoji-loader.js  
  inflating: wordpress/wp-includes/js/api-request.js  
  inflating: wordpress/wp-includes/js/wp-lists.min.js  
  inflating: wordpress/wp-includes/js/wp-a11y.min.js  
  inflating: wordpress/wp-includes/js/autosave.js  
  inflating: wordpress/wp-includes/js/wp-pointer.js  
  inflating: wordpress/wp-includes/js/zxcvbn-async.min.js  
  inflating: wordpress/wp-includes/js/utils.js  
  inflating: wordpress/wp-includes/js/wp-sanitize.min.js  
  inflating: wordpress/wp-includes/js/media-editor.min.js  
  inflating: wordpress/wp-includes/js/mce-view.js  
  inflating: wordpress/wp-includes/js/customize-base.js  
  inflating: wordpress/wp-includes/js/underscore.min.js  
  inflating: wordpress/wp-includes/js/customize-preview-nav-menus.js  
  inflating: wordpress/wp-includes/js/wp-backbone.js  
  inflating: wordpress/wp-includes/js/backbone.min.js  
   creating: wordpress/wp-includes/js/jquery/
  inflating: wordpress/wp-includes/js/jquery/jquery.masonry.min.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.color.min.js  
   creating: wordpress/wp-includes/js/jquery/ui/
  inflating: wordpress/wp-includes/js/jquery/ui/selectmenu.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/widget.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/sortable.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/droppable.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-size.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-pulsate.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-puff.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/datepicker.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/autocomplete.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/selectable.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/mouse.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/position.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/progressbar.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-explode.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/button.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/dialog.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/tabs.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/slider.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-slide.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/resizable.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-fold.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-blind.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-drop.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-highlight.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-fade.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-shake.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/accordion.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-scale.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/core.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/menu.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-transfer.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-clip.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/draggable.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/effect-bounce.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/spinner.min.js  
  inflating: wordpress/wp-includes/js/jquery/ui/tooltip.min.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.table-hotkeys.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.hotkeys.min.js  
  inflating: wordpress/wp-includes/js/jquery/suggest.min.js  
  inflating: wordpress/wp-includes/js/jquery/suggest.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.hotkeys.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.schedule.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.form.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.table-hotkeys.min.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.form.min.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.ui.touch-punch.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.serialize-object.js  
  inflating: wordpress/wp-includes/js/jquery/jquery-migrate.min.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.js  
  inflating: wordpress/wp-includes/js/jquery/jquery-migrate.js  
  inflating: wordpress/wp-includes/js/jquery/jquery.query.js  
  inflating: wordpress/wp-includes/js/wp-ajax-response.js  
  inflating: wordpress/wp-includes/js/colorpicker.js  
  inflating: wordpress/wp-includes/js/wp-util.min.js  
  inflating: wordpress/wp-includes/js/wp-emoji-loader.min.js  
  inflating: wordpress/wp-includes/js/media-models.js  
  inflating: wordpress/wp-includes/js/wplink.js  
  inflating: wordpress/wp-includes/js/media-editor.js  
  inflating: wordpress/wp-includes/js/wp-embed.min.js  
  inflating: wordpress/wp-includes/js/wpdialog.js  
  inflating: wordpress/wp-includes/js/autosave.min.js  
  inflating: wordpress/wp-includes/js/customize-views.min.js  
  inflating: wordpress/wp-includes/js/media-audiovideo.js  
  inflating: wordpress/wp-includes/js/mce-view.min.js  
  inflating: wordpress/wp-includes/js/hoverIntent.js  
   creating: wordpress/wp-includes/js/plupload/
  inflating: wordpress/wp-includes/js/plupload/wp-plupload.js  
  inflating: wordpress/wp-includes/js/plupload/wp-plupload.min.js  
  inflating: wordpress/wp-includes/js/plupload/plupload.js  
  inflating: wordpress/wp-includes/js/plupload/handlers.min.js  
  inflating: wordpress/wp-includes/js/plupload/moxie.js  
  inflating: wordpress/wp-includes/js/plupload/handlers.js  
  inflating: wordpress/wp-includes/js/plupload/license.txt  
  inflating: wordpress/wp-includes/js/plupload/moxie.min.js  
  inflating: wordpress/wp-includes/js/plupload/plupload.min.js  
  inflating: wordpress/wp-includes/js/wp-emoji-release.min.js  
  inflating: wordpress/wp-includes/js/wp-emoji.js  
  inflating: wordpress/wp-includes/js/wp-list-revisions.js  
  inflating: wordpress/wp-includes/js/quicktags.js  
  inflating: wordpress/wp-includes/js/wp-pointer.min.js  
  inflating: wordpress/wp-includes/js/media-models.min.js  
  inflating: wordpress/wp-includes/js/api-request.min.js  
  inflating: wordpress/wp-includes/js/twemoji.min.js  
  inflating: wordpress/wp-includes/js/hoverIntent.min.js  
  inflating: wordpress/wp-includes/js/customize-preview-widgets.min.js  
  inflating: wordpress/wp-includes/js/wp-embed-template.js  
  inflating: wordpress/wp-includes/js/shortcode.min.js  
  inflating: wordpress/wp-includes/js/wp-emoji.min.js  
  inflating: wordpress/wp-includes/js/wp-custom-header.js  
  inflating: wordpress/wp-includes/js/customize-models.min.js  
  inflating: wordpress/wp-includes/js/shortcode.js  
  inflating: wordpress/wp-includes/js/media-grid.min.js  
  inflating: wordpress/wp-includes/js/admin-bar.js  
  inflating: wordpress/wp-includes/js/wp-api.js  
  inflating: wordpress/wp-includes/js/quicktags.min.js  
  inflating: wordpress/wp-includes/js/wp-backbone.min.js  
  inflating: wordpress/wp-includes/js/tw-sack.min.js  
  inflating: wordpress/wp-includes/js/media-grid.js  
  inflating: wordpress/wp-includes/js/heartbeat.min.js  
  inflating: wordpress/wp-includes/js/customize-preview.min.js  
  inflating: wordpress/wp-includes/js/zxcvbn.min.js  
  inflating: wordpress/wp-includes/js/customize-loader.js  
  inflating: wordpress/wp-includes/js/heartbeat.js  
  inflating: wordpress/wp-includes/js/wp-auth-check.js  
  inflating: wordpress/wp-includes/js/customize-selective-refresh.min.js  
  inflating: wordpress/wp-includes/js/admin-bar.min.js  
  inflating: wordpress/wp-includes/js/media-views.js  
  inflating: wordpress/wp-includes/js/wp-util.js  
  inflating: wordpress/wp-includes/js/customize-selective-refresh.js  
  inflating: wordpress/wp-includes/js/json2.min.js  
  inflating: wordpress/wp-includes/js/customize-loader.min.js  
  inflating: wordpress/wp-includes/js/colorpicker.min.js  
  inflating: wordpress/wp-includes/js/wp-custom-header.min.js  
  inflating: wordpress/wp-includes/js/wp-embed.js  
  inflating: wordpress/wp-includes/js/masonry.min.js  
  inflating: wordpress/wp-includes/js/wp-api.min.js  
  inflating: wordpress/wp-includes/js/wp-lists.js  
  inflating: wordpress/wp-includes/js/twemoji.js  
  inflating: wordpress/wp-includes/js/customize-models.js  
  inflating: wordpress/wp-includes/js/json2.js  
  inflating: wordpress/wp-includes/js/customize-base.min.js  
  inflating: wordpress/wp-includes/js/media-audiovideo.min.js  
  inflating: wordpress/wp-includes/js/media-views.min.js  
   creating: wordpress/wp-includes/js/thickbox/
  inflating: wordpress/wp-includes/js/thickbox/macFFBgHack.png  
  inflating: wordpress/wp-includes/js/thickbox/thickbox.js  
  inflating: wordpress/wp-includes/js/thickbox/loadingAnimation.gif  
  inflating: wordpress/wp-includes/js/thickbox/thickbox.css  
  inflating: wordpress/wp-includes/js/customize-preview.js  
   creating: wordpress/wp-includes/js/swfupload/
  inflating: wordpress/wp-includes/js/swfupload/swfupload.js  
  inflating: wordpress/wp-includes/js/swfupload/handlers.min.js  
  inflating: wordpress/wp-includes/js/swfupload/handlers.js  
  inflating: wordpress/wp-includes/js/swfupload/license.txt  
  inflating: wordpress/wp-includes/js/wp-auth-check.min.js  
  inflating: wordpress/wp-includes/js/customize-preview-nav-menus.min.js  
  inflating: wordpress/wp-includes/js/tw-sack.js  
  inflating: wordpress/wp-includes/js/wp-ajax-response.min.js  
  inflating: wordpress/wp-includes/js/wp-sanitize.js  
  inflating: wordpress/wp-includes/js/customize-views.js  
   creating: wordpress/wp-includes/Text/
   creating: wordpress/wp-includes/Text/Diff/
   creating: wordpress/wp-includes/Text/Diff/Renderer/
  inflating: wordpress/wp-includes/Text/Diff/Renderer/inline.php  
   creating: wordpress/wp-includes/Text/Diff/Engine/
  inflating: wordpress/wp-includes/Text/Diff/Engine/native.php  
  inflating: wordpress/wp-includes/Text/Diff/Engine/shell.php  
  inflating: wordpress/wp-includes/Text/Diff/Engine/string.php  
  inflating: wordpress/wp-includes/Text/Diff/Engine/xdiff.php  
  inflating: wordpress/wp-includes/Text/Diff/Renderer.php  
  inflating: wordpress/wp-includes/Text/Diff.php  
  inflating: wordpress/wp-includes/formatting.php  
  inflating: wordpress/wp-includes/class-wp-term-query.php  
  inflating: wordpress/wp-includes/class-wp-walker.php  
  inflating: wordpress/wp-includes/class-wp-http-streams.php  
  inflating: wordpress/wp-includes/class-wp-metadata-lazyloader.php  
  inflating: wordpress/wp-includes/embed.php  
  inflating: wordpress/wp-includes/class-wp-site.php  
  inflating: wordpress/wp-includes/class-walker-page-dropdown.php  
  inflating: wordpress/wp-includes/class-wp-http-proxy.php  
  inflating: wordpress/wp-includes/class-wp-xmlrpc-server.php  
  inflating: wordpress/wp-includes/class-wp-locale.php  
  inflating: wordpress/wp-includes/link-template.php  
  inflating: wordpress/wp-includes/vars.php  
  inflating: wordpress/wp-includes/class.wp-dependencies.php  
  inflating: wordpress/wp-includes/class-wp-locale-switcher.php  
  inflating: wordpress/wp-includes/class-http.php  
  inflating: wordpress/wp-includes/date.php  
  inflating: wordpress/wp-includes/admin-bar.php  
  inflating: wordpress/wp-includes/class-wp-embed.php  
  inflating: wordpress/wp-includes/post-formats.php  
  inflating: wordpress/wp-includes/class-wp-ajax-response.php  
  inflating: wordpress/wp-includes/wlwmanifest.xml  
   creating: wordpress/wp-includes/theme-compat/
  inflating: wordpress/wp-includes/theme-compat/sidebar.php  
  inflating: wordpress/wp-includes/theme-compat/embed-404.php  
  inflating: wordpress/wp-includes/theme-compat/comments.php  
  inflating: wordpress/wp-includes/theme-compat/embed-content.php  
  inflating: wordpress/wp-includes/theme-compat/embed.php  
  inflating: wordpress/wp-includes/theme-compat/header-embed.php  
  inflating: wordpress/wp-includes/theme-compat/header.php  
  inflating: wordpress/wp-includes/theme-compat/footer-embed.php  
  inflating: wordpress/wp-includes/theme-compat/footer.php  
  inflating: wordpress/wp-includes/update.php  
  inflating: wordpress/wp-includes/ms-blogs.php  
  inflating: wordpress/wp-includes/class-simplepie.php  
  inflating: wordpress/wp-includes/class-wp-error.php  
  inflating: wordpress/wp-includes/plugin.php  
  inflating: wordpress/wp-includes/class-wp-image-editor-gd.php  
  inflating: wordpress/wp-includes/class-wp-customize-control.php  
  inflating: wordpress/wp-includes/class-wp-image-editor-imagick.php  
  inflating: wordpress/wp-includes/class-pop3.php  
  inflating: wordpress/wp-includes/class-phpmailer.php  
  inflating: wordpress/wp-includes/class.wp-styles.php  
  inflating: wordpress/wp-includes/class-snoopy.php  
   creating: wordpress/wp-includes/images/
  inflating: wordpress/wp-includes/images/toggle-arrow.png  
 extracting: wordpress/wp-includes/images/uploader-icons.png  
   creating: wordpress/wp-includes/images/crystal/
 extracting: wordpress/wp-includes/images/crystal/interactive.png  
 extracting: wordpress/wp-includes/images/crystal/video.png  
 extracting: wordpress/wp-includes/images/crystal/text.png  
 extracting: wordpress/wp-includes/images/crystal/archive.png  
 extracting: wordpress/wp-includes/images/crystal/audio.png  
  inflating: wordpress/wp-includes/images/crystal/license.txt  
 extracting: wordpress/wp-includes/images/crystal/spreadsheet.png  
 extracting: wordpress/wp-includes/images/crystal/code.png  
 extracting: wordpress/wp-includes/images/crystal/document.png  
 extracting: wordpress/wp-includes/images/crystal/default.png  
 extracting: wordpress/wp-includes/images/rss.png  
   creating: wordpress/wp-includes/images/media/
 extracting: wordpress/wp-includes/images/media/interactive.png  
 extracting: wordpress/wp-includes/images/media/video.png  
  inflating: wordpress/wp-includes/images/media/text.png  
 extracting: wordpress/wp-includes/images/media/archive.png  
 extracting: wordpress/wp-includes/images/media/audio.png  
  inflating: wordpress/wp-includes/images/media/spreadsheet.png  
 extracting: wordpress/wp-includes/images/media/code.png  
 extracting: wordpress/wp-includes/images/media/document.png  
  inflating: wordpress/wp-includes/images/media/default.png  
   creating: wordpress/wp-includes/images/wlw/
 extracting: wordpress/wp-includes/images/wlw/wp-icon.png  
 extracting: wordpress/wp-includes/images/wlw/wp-comments.png  
 extracting: wordpress/wp-includes/images/wlw/wp-watermark.png  
   creating: wordpress/wp-includes/images/smilies/
  inflating: wordpress/wp-includes/images/smilies/simple-smile.png  
  inflating: wordpress/wp-includes/images/smilies/icon_redface.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_mad.gif  
  inflating: wordpress/wp-includes/images/smilies/rolleyes.png  
  inflating: wordpress/wp-includes/images/smilies/icon_biggrin.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_question.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_sad.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_smile.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_mrgreen.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_surprised.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_wink.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_eek.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_rolleyes.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_exclaim.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_twisted.gif  
  inflating: wordpress/wp-includes/images/smilies/mrgreen.png  
  inflating: wordpress/wp-includes/images/smilies/icon_neutral.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_cool.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_arrow.gif  
  inflating: wordpress/wp-includes/images/smilies/frownie.png  
  inflating: wordpress/wp-includes/images/smilies/icon_confused.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_cry.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_razz.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_idea.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_lol.gif  
  inflating: wordpress/wp-includes/images/smilies/icon_evil.gif  
  inflating: wordpress/wp-includes/images/xit-2x.gif  
  inflating: wordpress/wp-includes/images/toggle-arrow-2x.png  
  inflating: wordpress/wp-includes/images/spinner-2x.gif  
  inflating: wordpress/wp-includes/images/uploader-icons-2x.png  
 extracting: wordpress/wp-includes/images/admin-bar-sprite.png  
  inflating: wordpress/wp-includes/images/wpspin-2x.gif  
  inflating: wordpress/wp-includes/images/down_arrow-2x.gif  
 extracting: wordpress/wp-includes/images/icon-pointer-flag-2x.png  
  inflating: wordpress/wp-includes/images/w-logo-blue.png  
  inflating: wordpress/wp-includes/images/down_arrow.gif  
  inflating: wordpress/wp-includes/images/wpicons-2x.png  
  inflating: wordpress/wp-includes/images/wpspin.gif  
 extracting: wordpress/wp-includes/images/icon-pointer-flag.png  
  inflating: wordpress/wp-includes/images/wpicons.png  
  inflating: wordpress/wp-includes/images/admin-bar-sprite-2x.png  
 extracting: wordpress/wp-includes/images/rss-2x.png  
  inflating: wordpress/wp-includes/images/spinner.gif  
  inflating: wordpress/wp-includes/images/blank.gif  
  inflating: wordpress/wp-includes/images/arrow-pointer-blue-2x.png  
 extracting: wordpress/wp-includes/images/xit.gif  
 extracting: wordpress/wp-includes/images/arrow-pointer-blue.png  
  inflating: wordpress/wp-includes/feed-rss.php  
  inflating: wordpress/wp-includes/functions.php  
  inflating: wordpress/wp-includes/compat.php  
  inflating: wordpress/wp-includes/widgets.php  
  inflating: wordpress/wp-includes/cache.php  
  inflating: wordpress/wp-includes/class-wp-meta-query.php  
  inflating: wordpress/wp-includes/template.php  
  inflating: wordpress/wp-includes/media-template.php  
   creating: wordpress/wp-includes/ID3/
  inflating: wordpress/wp-includes/ID3/module.tag.id3v1.php  
  inflating: wordpress/wp-includes/ID3/module.audio.ogg.php  
  inflating: wordpress/wp-includes/ID3/readme.txt  
  inflating: wordpress/wp-includes/ID3/module.tag.id3v2.php  
  inflating: wordpress/wp-includes/ID3/module.tag.apetag.php  
  inflating: wordpress/wp-includes/ID3/module.audio-video.asf.php  
  inflating: wordpress/wp-includes/ID3/module.audio-video.riff.php  
  inflating: wordpress/wp-includes/ID3/module.audio.ac3.php  
  inflating: wordpress/wp-includes/ID3/module.tag.lyrics3.php  
  inflating: wordpress/wp-includes/ID3/module.audio-video.flv.php  
  inflating: wordpress/wp-includes/ID3/module.audio.dts.php  
  inflating: wordpress/wp-includes/ID3/module.audio.flac.php  
  inflating: wordpress/wp-includes/ID3/license.txt  
  inflating: wordpress/wp-includes/ID3/getid3.php  
  inflating: wordpress/wp-includes/ID3/module.audio.mp3.php  
  inflating: wordpress/wp-includes/ID3/license.commercial.txt  
  inflating: wordpress/wp-includes/ID3/module.audio-video.quicktime.php  
  inflating: wordpress/wp-includes/ID3/module.audio-video.matroska.php  
  inflating: wordpress/wp-includes/ID3/getid3.lib.php  
  inflating: wordpress/wp-includes/class.wp-scripts.php  
  inflating: wordpress/wp-includes/ms-default-filters.php  
  inflating: wordpress/wp-includes/ms-settings.php  
  inflating: wordpress/wp-includes/category-template.php  
  inflating: wordpress/wp-includes/post.php  
  inflating: wordpress/wp-includes/class-wp-http-requests-hooks.php  
  inflating: wordpress/wp-includes/rest-api.php  
  inflating: wordpress/wp-includes/ms-functions.php  
  inflating: wordpress/wp-includes/ms-deprecated.php  
  inflating: wordpress/wp-includes/class-walker-category.php  
  inflating: wordpress/wp-includes/class-wp-http-curl.php  
  inflating: wordpress/wp-includes/wp-db.php  
  inflating: wordpress/wp-includes/class-wp-http-encoding.php  
  inflating: wordpress/wp-includes/class-wp-matchesmapregex.php  
   creating: wordpress/wp-includes/Requests/
  inflating: wordpress/wp-includes/Requests/Response.php  
   creating: wordpress/wp-includes/Requests/Auth/
  inflating: wordpress/wp-includes/Requests/Auth/Basic.php  
  inflating: wordpress/wp-includes/Requests/IRI.php  
  inflating: wordpress/wp-includes/Requests/Transport.php  
  inflating: wordpress/wp-includes/Requests/Exception.php  
   creating: wordpress/wp-includes/Requests/Cookie/
  inflating: wordpress/wp-includes/Requests/Cookie/Jar.php  
  inflating: wordpress/wp-includes/Requests/SSL.php  
  inflating: wordpress/wp-includes/Requests/Cookie.php  
  inflating: wordpress/wp-includes/Requests/IDNAEncoder.php  
  inflating: wordpress/wp-includes/Requests/Hooker.php  
  inflating: wordpress/wp-includes/Requests/IPv6.php  
  inflating: wordpress/wp-includes/Requests/Auth.php  
   creating: wordpress/wp-includes/Requests/Proxy/
  inflating: wordpress/wp-includes/Requests/Proxy/HTTP.php  
   creating: wordpress/wp-includes/Requests/Utility/
  inflating: wordpress/wp-includes/Requests/Utility/FilteredIterator.php  
  inflating: wordpress/wp-includes/Requests/Utility/CaseInsensitiveDictionary.php  
   creating: wordpress/wp-includes/Requests/Transport/
  inflating: wordpress/wp-includes/Requests/Transport/fsockopen.php  
  inflating: wordpress/wp-includes/Requests/Transport/cURL.php  
  inflating: wordpress/wp-includes/Requests/Hooks.php  
  inflating: wordpress/wp-includes/Requests/Proxy.php  
   creating: wordpress/wp-includes/Requests/Exception/
  inflating: wordpress/wp-includes/Requests/Exception/HTTP.php  
  inflating: wordpress/wp-includes/Requests/Exception/Transport.php  
   creating: wordpress/wp-includes/Requests/Exception/Transport/
  inflating: wordpress/wp-includes/Requests/Exception/Transport/cURL.php  
   creating: wordpress/wp-includes/Requests/Exception/HTTP/
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/428.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/409.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/403.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/402.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/503.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/306.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/414.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/502.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/429.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/404.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/405.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/401.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/305.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/418.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/410.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/412.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/504.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/400.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/417.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/407.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/304.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/511.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/500.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/505.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/415.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/416.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/408.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/501.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/431.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/Unknown.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/406.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/413.php  
  inflating: wordpress/wp-includes/Requests/Exception/HTTP/411.php  
  inflating: wordpress/wp-includes/Requests/Session.php  
   creating: wordpress/wp-includes/Requests/Response/
  inflating: wordpress/wp-includes/Requests/Response/Headers.php  
  inflating: wordpress/wp-includes/feed-rss2.php  
  inflating: wordpress/wp-includes/comment.php  
  inflating: wordpress/wp-includes/meta.php  
  inflating: wordpress/wp-includes/rewrite.php  
  inflating: wordpress/wp-includes/class-wp-network.php  
  inflating: wordpress/wp-includes/post-template.php  
  inflating: wordpress/wp-includes/pluggable-deprecated.php  
  inflating: wordpress/wp-includes/user.php  
  inflating: wordpress/wp-includes/pluggable.php  
  inflating: wordpress/wp-includes/class-wp-feed-cache-transient.php  
  inflating: wordpress/wp-includes/class-wp-role.php  
  inflating: wordpress/wp-includes/canonical.php  
  inflating: wordpress/wp-includes/locale.php  
  inflating: wordpress/wp-includes/theme.php  
  inflating: wordpress/wp-includes/class-wp-term.php  
  inflating: wordpress/wp-includes/l10n.php  
  inflating: wordpress/wp-includes/class-wp-post-type.php  
  inflating: wordpress/wp-includes/class-wp-simplepie-file.php  
  inflating: wordpress/wp-includes/feed-rss2-comments.php  
  inflating: wordpress/wp-includes/class-wp-text-diff-renderer-table.php  
  inflating: wordpress/wp-includes/kses.php  
  inflating: wordpress/wp-includes/script-loader.php  
  inflating: wordpress/wp-includes/class-wp-site-query.php  
  inflating: wordpress/wp-includes/class-wp-http-requests-response.php  
  inflating: wordpress/wp-includes/default-filters.php  
   creating: wordpress/wp-includes/SimplePie/
  inflating: wordpress/wp-includes/SimplePie/Category.php  
  inflating: wordpress/wp-includes/SimplePie/Source.php  
  inflating: wordpress/wp-includes/SimplePie/IRI.php  
  inflating: wordpress/wp-includes/SimplePie/Restriction.php  
   creating: wordpress/wp-includes/SimplePie/Net/
  inflating: wordpress/wp-includes/SimplePie/Net/IPv6.php  
  inflating: wordpress/wp-includes/SimplePie/File.php  
  inflating: wordpress/wp-includes/SimplePie/Exception.php  
  inflating: wordpress/wp-includes/SimplePie/Sanitize.php  
  inflating: wordpress/wp-includes/SimplePie/Copyright.php  
  inflating: wordpress/wp-includes/SimplePie/Misc.php  
  inflating: wordpress/wp-includes/SimplePie/Caption.php  
  inflating: wordpress/wp-includes/SimplePie/Locator.php  
  inflating: wordpress/wp-includes/SimplePie/Rating.php  
  inflating: wordpress/wp-includes/SimplePie/Registry.php  
  inflating: wordpress/wp-includes/SimplePie/Parser.php  
  inflating: wordpress/wp-includes/SimplePie/Enclosure.php  
   creating: wordpress/wp-includes/SimplePie/Content/
   creating: wordpress/wp-includes/SimplePie/Content/Type/
  inflating: wordpress/wp-includes/SimplePie/Content/Type/Sniffer.php  
   creating: wordpress/wp-includes/SimplePie/Decode/
   creating: wordpress/wp-includes/SimplePie/Decode/HTML/
  inflating: wordpress/wp-includes/SimplePie/Decode/HTML/Entities.php  
   creating: wordpress/wp-includes/SimplePie/Cache/
  inflating: wordpress/wp-includes/SimplePie/Cache/DB.php  
  inflating: wordpress/wp-includes/SimplePie/Cache/Base.php  
  inflating: wordpress/wp-includes/SimplePie/Cache/File.php  
  inflating: wordpress/wp-includes/SimplePie/Cache/MySQL.php  
  inflating: wordpress/wp-includes/SimplePie/Cache/Memcache.php  
  inflating: wordpress/wp-includes/SimplePie/Core.php  
   creating: wordpress/wp-includes/SimplePie/HTTP/
  inflating: wordpress/wp-includes/SimplePie/HTTP/Parser.php  
   creating: wordpress/wp-includes/SimplePie/Parse/
  inflating: wordpress/wp-includes/SimplePie/Parse/Date.php  
  inflating: wordpress/wp-includes/SimplePie/Credit.php  
  inflating: wordpress/wp-includes/SimplePie/gzdecode.php  
  inflating: wordpress/wp-includes/SimplePie/Author.php  
   creating: wordpress/wp-includes/SimplePie/XML/
   creating: wordpress/wp-includes/SimplePie/XML/Declaration/
  inflating: wordpress/wp-includes/SimplePie/XML/Declaration/Parser.php  
  inflating: wordpress/wp-includes/SimplePie/Cache.php  
  inflating: wordpress/wp-includes/SimplePie/Item.php  
  inflating: wordpress/wp-includes/http.php  
  inflating: wordpress/wp-includes/ms-load.php  
  inflating: wordpress/wp-includes/feed-atom-comments.php  
  inflating: wordpress/wp-includes/class-wp-user.php  
  inflating: wordpress/wp-includes/media.php  
  inflating: wordpress/wp-includes/class-wp-dependency.php  
  inflating: wordpress/wp-includes/class-wp-editor.php  
  inflating: wordpress/wp-includes/class-walker-page.php  
  inflating: wordpress/wp-includes/class-wp-oembed-controller.php  
  inflating: wordpress/wp-includes/class-wp-list-util.php  
  inflating: wordpress/wp-includes/class-phpass.php  
  inflating: wordpress/wp-includes/ms-files.php  
  inflating: wordpress/wp-includes/class-wp-customize-widgets.php  
  inflating: wordpress/wp-includes/functions.wp-scripts.php  
  inflating: wordpress/wp-includes/class-walker-nav-menu.php  
  inflating: wordpress/wp-includes/class-wp-user-meta-session-tokens.php  
  inflating: wordpress/wp-includes/class-wp-admin-bar.php  
  inflating: wordpress/wp-includes/class-wp-http-ixr-client.php  
  inflating: wordpress/wp-includes/general-template.php  
   creating: wordpress/wp-includes/random_compat/
  inflating: wordpress/wp-includes/random_compat/error_polyfill.php  
  inflating: wordpress/wp-includes/random_compat/random_int.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_libsodium.php  
  inflating: wordpress/wp-includes/random_compat/byte_safe_strings.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_com_dotnet.php  
  inflating: wordpress/wp-includes/random_compat/random.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_mcrypt.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_dev_urandom.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_openssl.php  
  inflating: wordpress/wp-includes/random_compat/cast_to_int.php  
  inflating: wordpress/wp-includes/random_compat/random_bytes_libsodium_legacy.php  
  inflating: wordpress/wp-includes/class-requests.php  
  inflating: wordpress/wp-includes/functions.wp-styles.php  
  inflating: wordpress/wp-includes/class-wp-http-response.php  
  inflating: wordpress/wp-includes/registration-functions.php  
  inflating: wordpress/wp-includes/shortcodes.php  
  inflating: wordpress/wp-includes/class-IXR.php  
  inflating: wordpress/wp-includes/rss-functions.php  
   creating: wordpress/wp-includes/css/
  inflating: wordpress/wp-includes/css/dashicons.min.css  
  inflating: wordpress/wp-includes/css/customize-preview.css  
  inflating: wordpress/wp-includes/css/customize-preview-rtl.min.css  
  inflating: wordpress/wp-includes/css/editor.min.css  
  inflating: wordpress/wp-includes/css/wp-auth-check-rtl.min.css  
  inflating: wordpress/wp-includes/css/dashicons.css  
  inflating: wordpress/wp-includes/css/jquery-ui-dialog.min.css  
  inflating: wordpress/wp-includes/css/wp-embed-template.min.css  
  inflating: wordpress/wp-includes/css/wp-pointer.min.css  
  inflating: wordpress/wp-includes/css/customize-preview.min.css  
  inflating: wordpress/wp-includes/css/buttons-rtl.css  
  inflating: wordpress/wp-includes/css/admin-bar-rtl.min.css  
  inflating: wordpress/wp-includes/css/media-views-rtl.css  
  inflating: wordpress/wp-includes/css/wp-embed-template.css  
  inflating: wordpress/wp-includes/css/editor.css  
  inflating: wordpress/wp-includes/css/buttons-rtl.min.css  
  inflating: wordpress/wp-includes/css/wp-embed-template-ie.min.css  
  inflating: wordpress/wp-includes/css/admin-bar.css  
  inflating: wordpress/wp-includes/css/wp-pointer.css  
  inflating: wordpress/wp-includes/css/jquery-ui-dialog-rtl.css  
  inflating: wordpress/wp-includes/css/jquery-ui-dialog.css  
  inflating: wordpress/wp-includes/css/buttons.css  
  inflating: wordpress/wp-includes/css/admin-bar.min.css  
  inflating: wordpress/wp-includes/css/wp-auth-check.min.css  
  inflating: wordpress/wp-includes/css/wp-pointer-rtl.min.css  
  inflating: wordpress/wp-includes/css/media-views.css  
  inflating: wordpress/wp-includes/css/wp-embed-template-ie.css  
  inflating: wordpress/wp-includes/css/media-views-rtl.min.css  
  inflating: wordpress/wp-includes/css/wp-pointer-rtl.css  
  inflating: wordpress/wp-includes/css/editor-rtl.min.css  
  inflating: wordpress/wp-includes/css/media-views.min.css  
  inflating: wordpress/wp-includes/css/editor-rtl.css  
  inflating: wordpress/wp-includes/css/wp-auth-check-rtl.css  
  inflating: wordpress/wp-includes/css/wp-auth-check.css  
  inflating: wordpress/wp-includes/css/customize-preview-rtl.css  
  inflating: wordpress/wp-includes/css/jquery-ui-dialog-rtl.min.css  
  inflating: wordpress/wp-includes/css/buttons.min.css  
  inflating: wordpress/wp-includes/css/admin-bar-rtl.css  
  inflating: wordpress/wp-includes/class-wp-query.php  
```
- Comprobamos que esta descomprimido correctamente.

```console
roberto@serverob:/var/www/html$ ls -l wordpress/
total 212
-rwxrwxrwx  1 root     root       418 sep 25  2013 index.php
-rwxrwxrwx  1 root     root     17935 dic  7 21:00 licencia.txt
-rwxrwxrwx  1 root     root     19935 ene  2  2017 license.txt
-rwxrwxrwx  1 root     root      7636 dic  7 21:00 readme.html
-rwxrwxrwx  1 root     root      5434 sep 23 12:21 wp-activate.php
drwxrwxrwx  9 root     root      4096 dic  7 21:00 wp-admin
-rwxrwxrwx  1 root     root       364 dic 19  2015 wp-blog-header.php
-rwxrwxrwx  1 root     root      1627 ago 29  2016 wp-comments-post.php
-rw-rw-rw-  1 www-data www-data  3198 dic 15 09:55 wp-config.php
-rwxrwxrwx  1 root     root      3237 dic  7 21:00 wp-config-sample.php
drwxrwxrwx  5 root     root      4096 dic 15 09:53 wp-content
-rwxrwxrwx  1 root     root      3669 ago 20 04:37 wp-cron.php
drwxrwxrwx 18 root     root     12288 dic  7 21:00 wp-includes
-rwxrwxrwx  1 root     root      2422 nov 21  2016 wp-links-opml.php
-rwxrwxrwx  1 root     root      3306 ago 22 11:52 wp-load.php
-rwxrwxrwx  1 root     root     36583 oct 13 02:10 wp-login.php
-rwxrwxrwx  1 root     root      8048 ene 11  2017 wp-mail.php
-rwxrwxrwx  1 root     root     16246 oct  4 00:20 wp-settings.php
-rwxrwxrwx  1 root     root     30071 oct 18 17:36 wp-signup.php
-rwxrwxrwx  1 root     root      4620 oct 23 22:12 wp-trackback.php
-rwxrwxrwx  1 root     root      3065 ago 31  2016 xmlrpc.php
roberto@serverob:/var/www/html$
```
- Abrimos un navegador y comenzamos con la instalación.


![](img/012.png)

- Comenzamos con la instalación.

![](img/013.png)

- Establecemos la base de datos que teniamos creada `cms` con el usuario `cms`

![](img/014.png)

- Ejecutamos la instalación.

![](img/015.png)

- Ya tenemos instalado el `Wordpress`

![](img/016.png)

- Accedemos al Wordpress

![](img/017.png)

- Comprobamos que podemos acceder al wordpress y ver las plantillas.

![](img/018.png)
