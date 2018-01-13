# Servicio FTP en Ubuntu

## 1. Instalación de FTP en Ubuntu

Primero tenemos que actualizar los repositios de Ubuntu.

- `sudo apt update`

```console
roberto@serverob:~$ sudo apt update
[sudo] password for roberto:
Obj:1 http://es.archive.ubuntu.com/ubuntu xenial InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu xenial-updates InRelease             
Des:3 http://security.ubuntu.com/ubuntu xenial-security InRelease [102 kB]     
Obj:4 http://es.archive.ubuntu.com/ubuntu xenial-backports InRelease           
Des:5 http://security.ubuntu.com/ubuntu xenial-security/main amd64 Packages [424 kB]
Des:6 http://security.ubuntu.com/ubuntu xenial-security/main i386 Packages [384 kB]
Des:7 http://security.ubuntu.com/ubuntu xenial-security/main Translation-en [186 kB]
Des:8 http://security.ubuntu.com/ubuntu xenial-security/restricted amd64 Packages [7.224 B]
Des:9 http://security.ubuntu.com/ubuntu xenial-security/restricted i386 Packages [7.224 B]
Des:10 http://security.ubuntu.com/ubuntu xenial-security/restricted Translation-en [2.152 B]
Des:11 http://security.ubuntu.com/ubuntu xenial-security/universe amd64 Packages [195 kB]
Des:12 http://security.ubuntu.com/ubuntu xenial-security/universe i386 Packages [160 kB]
Des:13 http://security.ubuntu.com/ubuntu xenial-security/universe Translation-en [101 kB]
Des:14 http://security.ubuntu.com/ubuntu xenial-security/multiverse amd64 Packages [3.208 B]
Des:15 http://security.ubuntu.com/ubuntu xenial-security/multiverse i386 Packages [3.380 B]
Descargados 1.574 kB en 1s (1.219 kB/s)
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se pueden actualizar 386 paquetes. Ejecute «apt list --upgradable» para verlos.

```

Para instalar el servicio `proftpd` tenemos que escribir el siguiente comando.

- `sudo apt install proftpd`

```console

roberto@serverob:~$ sudo apt install proftpd
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Nota, seleccionando «proftpd-basic» en lugar de «proftpd»
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  linux-headers-4.4.0-21 linux-headers-4.4.0-21-generic
  linux-image-4.4.0-21-generic linux-image-extra-4.4.0-21-generic
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  libmemcached11 libmemcachedutil2
Paquetes sugeridos:
  openbsd-inetd | inet-superserver proftpd-doc proftpd-mod-ldap
  proftpd-mod-mysql proftpd-mod-odbc proftpd-mod-pgsql proftpd-mod-sqlite
  proftpd-mod-geoip
Se instalarán los siguientes paquetes NUEVOS:
  libmemcached11 libmemcachedutil2 proftpd-basic
0 actualizados, 3 nuevos se instalarán, 0 para eliminar y 386 no actualizados.
Se necesita descargar 2.081 kB de archivos.
Se utilizarán 4.772 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libmemcached11 amd64 1.0.18-4.1 [82,7 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 libmemcachedutil2 amd64 1.0.18-4.1 [9.490 B]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial/universe amd64 proftpd-basic amd64 1.3.5a-1build1 [1.989 kB]
Descargados 2.081 kB en 2s (815 kB/s)      
Preconfigurando paquetes ...
Seleccionando el paquete libmemcached11:amd64 previamente no seleccionado.
(Leyendo la base de datos ... 267227 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../libmemcached11_1.0.18-4.1_amd64.deb ...
Desempaquetando libmemcached11:amd64 (1.0.18-4.1) ...
Seleccionando el paquete libmemcachedutil2:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libmemcachedutil2_1.0.18-4.1_amd64.deb ...
Desempaquetando libmemcachedutil2:amd64 (1.0.18-4.1) ...
Seleccionando el paquete proftpd-basic previamente no seleccionado.
Preparando para desempaquetar .../proftpd-basic_1.3.5a-1build1_amd64.deb ...
Desempaquetando proftpd-basic (1.3.5a-1build1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu9) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para man-db (2.7.5-1) ...
Configurando libmemcached11:amd64 (1.0.18-4.1) ...
Configurando libmemcachedutil2:amd64 (1.0.18-4.1) ...
Configurando proftpd-basic (1.3.5a-1build1) ...
Aviso: No se puede acceder al directorio personal /run/proftpd que especificó: No such file or directory.
Añadiendo el usuario del sistema `proftpd' (UID 124) ...
Añadiendo un nuevo usuario `proftpd' (UID 124) con grupo `nogroup' ...
No se crea el directorio personal `/run/proftpd'.
Añadiendo el usuario del sistema `ftp' (UID 125) ...
Añadiendo un nuevo usuario `ftp' (UID 125) con grupo `nogroup' ...
Creando el directorio personal `/srv/ftp' ...
'/usr/share/proftpd/templates/welcome.msg' -> '/srv/ftp/welcome.msg.proftpd-new'
Procesando disparadores para libc-bin (2.23-0ubuntu9) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
roberto@serverob:~$

```
En un instante de la instalación nos pedirá que seleccionemos dos opciones.

![](img/001.png)

- `Inetd`: Para pocas conexiones diarias.
- `Independiente`: Para muchas conexiones diarias.

### 2.1 Añadir en el DNS bind el alias ftp.miempresa.edu

Solo tenemos que ir al fichero de configuración de bind `/etc/bind/db.miempresa.edu`

```console
kevin@serverob:~$ sudo cat /etc/bind/db.miempresa

;
; BIND data file for local loopback interface
;
$TTL	604800
@	IN	SOA	miempresa.edu. root.miempresa.edu. (
			3
			604800
			86400
			2419200
			604800 )
;

@				IN	NS		miempresa.edu.
@				IN	A		172.18.22.1
@				IN	MX	0	miempresa.edu.
server				IN	A		172.18.22.1
www.miempresa.edu.		IN	CNAME		miempresa.edu.
pagos.miempresa.edu.		IN	CNAME		miempresa.edu.
phpmyadmin.miempresa.edu.	IN	CNAME		miempresa.edu.
empleados.miempresa.edu.	IN	CNAME		miempresa.edu.
ftp.miempresa.edu.		IN	CNAME		miempresa.edu.
kevin@serverob:~$ nslookup ftp.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

** server can't find ftp.miempresa.edu: NXDOMAIN

kevin@serverob:~$ nslookup ftp.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

** server can't find ftp.miempresa.edu: NXDOMAIN

kevin@serverob:~$ sudo systemctl restart bind9
Enter passphrase for SSL/TLS keys for pagos.miempresa.com:443 (RSA): *********
kevin@serverob:~$ nslookup ftp.miempresa.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

ftp.miempresa.edu	canonical name = miempresa.edu.
Name:	miempresa.edu
Address: 172.18.22.1

kevin@serverob:~$
```

### 1.2 Comprobar el fichero proftpd.conf

Tenemos que ir a la siguiente ruta `/etc/proftpd`

```console
kevin@serverob:~$ sudo scp scp?.txt kevin@172.18.22.1:/tmp
kevin@172.18.22.1's password:
scp1.txt                                      100%    0     0.0KB/s   00:00    
scp2.txt                                      100%    0     0.0KB/s   00:00    
scp3.txt                                      100%    0     0.0KB/s   00:00    
kevin@serverob:~$ sudo scp scp?.txt suso@172.18.22.1:/tmp
suso@172.18.22.1's password:
scp: /tmp/scp1.txt: Permission denied
scp: /tmp/scp2.txt: Permission denied
scp: /tmp/scp3.txt: Permission denied
kevin@serverob:~$ ls -l /tmp/
total 8
-rw------- 1 kevin kevin    0 ene 13 11:39 config-err-76NOz2
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp1.txt
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp2.txt
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp3.txt
drwx------ 3 root  root  4096 ene 13 11:18 systemd-private-feb28b88fc3246358c0616864e7abd13-colord.service-jSgaPc
drwx------ 3 root  root  4096 ene 13 11:18 systemd-private-feb28b88fc3246358c0616864e7abd13-rtkit-daemon.service-gYy6tx
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:39 unity_support_test.1
kevin@serverob:~$
```
- Comprobamos el fichero de configuración de proftpd

```console
kevin@serverob:/etc/proftpd$ sudo more proftpd.conf
#
# /etc/proftpd/proftpd.conf -- This is a basic ProFTPD configuration file.
# To really apply changes, reload proftpd after modifications, if
# it runs in daemon mode. It is not required in inetd/xinetd mode.
#

# Includes DSO modules
Include /etc/proftpd/modules.conf

# Set off to disable IPv6 support which is annoying on IPv4 only boxes.
UseIPv6				on
# If set on you can experience a longer connection delay in many cases.
IdentLookups			off

ServerName			"Debian"
ServerType			standalone
DeferWelcome			off

MultilineRFC2228		on
DefaultServer			on
ShowSymlinks			on

TimeoutNoTransfer		600
TimeoutStalled			600
TimeoutIdle			1200

DisplayLogin                    welcome.msg
DisplayChdir               	.message true
ListOptions                	"-l"

DenyFilter			\*.*/

# Use this to jail all users in their homes
# DefaultRoot			~

# Users require a valid shell listed in /etc/shells to login.
# Use this directive to release that constrain.
# RequireValidShell		off

# Port 21 is the standard FTP port.
Port				21

# In some cases you have to specify passive ports range to by-pass
# firewall limitations. Ephemeral ports can be used for that, but
# feel free to use a more narrow range.
# PassivePorts                  49152 65534

# If your host was NATted, this option is useful in order to
# allow passive tranfers to work. You have to use your public
# address and opening the passive ports used on your firewall as well.
# MasqueradeAddress		1.2.3.4

# This is useful for masquerading address with dynamic IPs:
# refresh any configured MasqueradeAddress directives every 8 hours
<IfModule mod_dynmasq.c>
# DynMasqRefresh 28800
</IfModule>

# To prevent DoS attacks, set the maximum number of child processes
# to 30.  If you need to allow more than 30 concurrent connections
# at once, simply increase this value.  Note that this ONLY works
# in standalone mode, in inetd mode you should use an inetd server
# that allows you to limit maximum number of processes per service
# (such as xinetd)
MaxInstances			30

# Set the user and group that the server normally runs at.
User				proftpd
Group				nogroup

# Umask 022 is a good standard umask to prevent new files and dirs
# (second parm) from being group and world writable.
Umask				022  022
# Normally, we want files to be overwriteable.
AllowOverwrite			on

# Uncomment this if you are using NIS or LDAP via NSS to retrieve passwords:
# PersistentPasswd		off

# This is required to use both PAM-based authentication and local passwords
# AuthOrder			mod_auth_pam.c* mod_auth_unix.c

# Be warned: use of this directive impacts CPU average load!
# Uncomment this if you like to see progress and transfer rate with ftpwho
# in downloads. That is not needed for uploads rates.
#
# UseSendFile			off

TransferLog /var/log/proftpd/xferlog
SystemLog   /var/log/proftpd/proftpd.log

# Logging onto /var/log/lastlog is enabled but set to off by default
#UseLastlog on

# In order to keep log file dates consistent after chroot, use timezone info
# from /etc/localtime.  If this is not set, and proftpd is configured to
# chroot (e.g. DefaultRoot or <Anonymous>), it will use the non-daylight
# savings timezone regardless of whether DST is in effect.
#SetEnv TZ :/etc/localtime

<IfModule mod_quotatab.c>
QuotaEngine off
</IfModule>

<IfModule mod_ratio.c>
Ratios off
</IfModule>


# Delay engine reduces impact of the so-called Timing Attack described in
# http://www.securityfocus.com/bid/11430/discuss
# It is on by default.
<IfModule mod_delay.c>
DelayEngine on
</IfModule>

<IfModule mod_ctrls.c>
ControlsEngine        off
ControlsMaxClients    2
ControlsLog           /var/log/proftpd/controls.log
ControlsInterval      5
ControlsSocket        /var/run/proftpd/proftpd.sock
</IfModule>

<IfModule mod_ctrls_admin.c>
AdminControlsEngine off
</IfModule>

#
# Alternative authentication frameworks
#
#Include /etc/proftpd/ldap.conf
#Include /etc/proftpd/sql.conf

#
# This is used for FTPS connections
#
#Include /etc/proftpd/tls.conf

#
# Useful to keep VirtualHost/VirtualRoot directives separated
#
#Include /etc/proftpd/virtuals.conf

# A basic anonymous configuration, no upload directories.

# <Anonymous ~ftp>
#   User				ftp
#   Group				nogroup
#   # We want clients to be able to login with "anonymous" as well as "ftp"
#   UserAlias			anonymous ftp
#   # Cosmetic changes, all files belongs to ftp user
#   DirFakeUser	on ftp
#   DirFakeGroup on ftp
#
#   RequireValidShell		off
#
#   # Limit the maximum number of anonymous logins
#   MaxClients			10
#
#   # We want 'welcome.msg' displayed at login, and '.message' displayed
#   # in each newly chdired directory.
#   DisplayLogin			welcome.msg
#   DisplayChdir		.message
#
#   # Limit WRITE everywhere in the anonymous chroot
#   <Directory *>
#     <Limit WRITE>
#       DenyAll
#     </Limit>
#   </Directory>
#
#   # Uncomment this if you're brave.
#   # <Directory incoming>
#   #   # Umask 022 is a good standard umask to prevent new files and dirs
#   #   # (second parm) from being group and world writable.
#   #   Umask				022  022
#   #            <Limit READ WRITE>
#   #            DenyAll
#   #            </Limit>
#   #            <Limit STOR>
#   #            AllowAll
#   #            </Limit>
#   # </Directory>
#
# </Anonymous>

# Include other custom configuration files
Include /etc/proftpd/conf.d/
kevin@serverob:/etc/proftpd$
```

### 1.2.1 Conexión al proftpd mediante el equipo cliente.

Comprobamos con el usuario administrador `kevin`

- Podemos acceder al home y también a la raíz de `/`

```console
roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): kevin
331 ContraseÃ±a necesaria para kevin
Password:
230 Usuario kevin conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Descargas
-rw-rw-r--   1 kevin    kevin          22 Jan 13 11:28 descarga.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Documentos
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Escritorio
-rw-r--r--   1 kevin    kevin        8980 Jan 12 10:19 examples.desktop
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Im??genes
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 M??sica
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Plantillas
-rw-r--r--   1 kevin    kevin           0 Jan 13 12:13 proftpddescarga.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 P??blico
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp1.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp2.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp3.txt
-rw-rw-r--   1 kevin    kevin          20 Jan 13 11:28 subido.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 V??deos
226 Transferencia completada
ftp> cd /
250 Comando 'CWD' exitoso
ftp> dir
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 bin
drwxr-xr-x   3 root     root         4096 Dec 15 08:34 boot
drwxrwxr-x   2 root     root         4096 Sep 19 12:27 cdrom
drwxr-xr-x  19 root     root         3940 Jan 13 11:18 dev
drwxr-xr-x 137 root     root        12288 Jan 13 11:18 etc
drwxr-xr-x   5 root     root         4096 Jan 12 10:19 home
lrwxrwxrwx   1 root     root           33 Dec 15 08:33 initrd.img -> boot/initrd.img-4.4.0-104-generic
lrwxrwxrwx   1 root     root           33 Dec 14 08:21 initrd.img.old -> boot/initrd.img-4.4.0-103-generic
drwxr-xr-x  22 root     root         4096 Sep 19 12:29 lib
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 lib64
drwx------   2 root     root        16384 Sep 19 12:25 lost+found
drwxr-xr-x   3 root     root         4096 Sep 19 15:01 media
drwxr-xr-x   2 root     root         4096 Apr 20  2016 mnt
drwxr-xr-x   3 root     root         4096 Sep 19 15:02 opt
dr-xr-xr-x 180 root     root            0 Jan 13 11:17 proc
drwx------   6 root     root         4096 Jan 13 11:48 root
drwxr-xr-x  30 root     root          980 Jan 13 11:49 run
drwxr-xr-x   2 root     root        12288 Dec 14 08:20 sbin
drwxr-xr-x   2 root     root         4096 Apr 19  2016 snap
drwxr-xr-x   3 root     root         4096 Jan 12 10:14 srv
dr-xr-xr-x  13 root     root            0 Jan 13 11:50 sys
drwxrwxrwt  10 root     root         4096 Jan 13 12:09 tmp
drwxr-xr-x  11 root     root         4096 Apr 20  2016 usr
drwxr-xr-x  16 root     root         4096 Dec 19 13:57 var
lrwxrwxrwx   1 root     root           30 Dec 15 08:33 vmlinuz -> boot/vmlinuz-4.4.0-104-generic
lrwxrwxrwx   1 root     root           30 Dec 14 08:21 vmlinuz.old -> boot/vmlinuz-4.4.0-103-generic
-rw-r--r--   1 root     root         2084 Dec 19 13:57 webmin-setup.out
226 Transferencia completada
ftp>
```
- Vamos a subir y descargar un fichero desde el equipo cliente al servidor con el usuario kevin.

```console
roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): kevin
331 ContraseÃ±a necesaria para kevin
Password:
230 Usuario kevin conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Descargas
-rw-rw-r--   1 kevin    kevin          22 Jan 13 11:28 descarga.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Documentos
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Escritorio
-rw-r--r--   1 kevin    kevin        8980 Jan 12 10:19 examples.desktop
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Im??genes
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 M??sica
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Plantillas
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 P??blico
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp1.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp2.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp3.txt
-rw-rw-r--   1 kevin    kevin          20 Jan 13 11:28 subido.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 V??deos
226 Transferencia completada
ftp> put proftpddescarga.txt
local: proftpddescarga.txt remote: proftpddescarga.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpddescarga.txt
226 Transferencia completada
ftp> put proftpsubida.txt
local: proftpsubida.txt remote: proftpsubida.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpsubida.txt
226 Transferencia completada
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Descargas
-rw-rw-r--   1 kevin    kevin          22 Jan 13 11:28 descarga.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Documentos
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Escritorio
-rw-r--r--   1 kevin    kevin        8980 Jan 12 10:19 examples.desktop
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Im??genes
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 M??sica
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Plantillas
-rw-r--r--   1 kevin    kevin           0 Jan 13 12:20 proftpddescarga.txt
-rw-r--r--   1 kevin    kevin           0 Jan 13 12:21 proftpsubida.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 P??blico
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp1.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp2.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp3.txt
-rw-rw-r--   1 kevin    kevin          20 Jan 13 11:28 subido.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 V??deos
226 Transferencia completada
ftp> get proftpddescarga.txt
local: proftpddescarga.txt remote: proftpddescarga.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpddescarga.txt
226 Transferencia completada
ftp>
```
- Comprobamos el acceso con el usuario Suso

```console

roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): suso
331 ContraseÃ±a necesaria para suso
Password:
230 Usuario suso conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> cd /
250 Comando 'CWD' exitoso
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 bin
drwxr-xr-x   3 root     root         4096 Dec 15 08:34 boot
drwxrwxr-x   2 root     root         4096 Sep 19 12:27 cdrom
drwxr-xr-x  19 root     root         3940 Jan 13 11:18 dev
drwxr-xr-x 137 root     root        12288 Jan 13 11:18 etc
drwxr-xr-x   5 root     root         4096 Jan 12 10:19 home
lrwxrwxrwx   1 root     root           33 Dec 15 08:33 initrd.img -> boot/initrd.img-4.4.0-104-generic
lrwxrwxrwx   1 root     root           33 Dec 14 08:21 initrd.img.old -> boot/initrd.img-4.4.0-103-generic
drwxr-xr-x  22 root     root         4096 Sep 19 12:29 lib
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 lib64
drwx------   2 root     root        16384 Sep 19 12:25 lost+found
drwxr-xr-x   3 root     root         4096 Sep 19 15:01 media
drwxr-xr-x   2 root     root         4096 Apr 20  2016 mnt
drwxr-xr-x   3 root     root         4096 Sep 19 15:02 opt
dr-xr-xr-x 183 root     root            0 Jan 13 11:17 proc
drwx------   6 root     root         4096 Jan 13 11:48 root
drwxr-xr-x  30 root     root          980 Jan 13 11:49 run
drwxr-xr-x   2 root     root        12288 Dec 14 08:20 sbin
drwxr-xr-x   2 root     root         4096 Apr 19  2016 snap
drwxr-xr-x   3 root     root         4096 Jan 12 10:14 srv
dr-xr-xr-x  13 root     root            0 Jan 13 11:50 sys
drwxrwxrwt  10 root     root         4096 Jan 13 12:17 tmp
drwxr-xr-x  11 root     root         4096 Apr 20  2016 usr
drwxr-xr-x  16 root     root         4096 Dec 19 13:57 var
lrwxrwxrwx   1 root     root           30 Dec 15 08:33 vmlinuz -> boot/vmlinuz-4.4.0-104-generic
lrwxrwxrwx   1 root     root           30 Dec 14 08:21 vmlinuz.old -> boot/vmlinuz-4.4.0-103-generic
-rw-r--r--   1 root     root         2084 Dec 19 13:57 webmin-setup.out
226 Transferencia completada
ftp>
```
- Comprobamos que este usuario tambiíen puede acceder a la raíz. No es un usuario administrador, vamos a crear una regla para que no pueda acceder este cliente a la raíz del `sistema operativo ubuntu`. Solo tenemos que ir al fichero `proftpd.conf` y modificar la siguientes líneas donde se encuentra `DefaultRoot`

``` console
kevin@serverob:/etc/proftpd$ more proftpd.conf | grep -e suso -e kevin
DefaultRoot			/home/suso 	suso
DefaultRoot			/		kevin
kevin@serverob:/etc/proftpd$
```

- Si nos fijamos tenemos establecido una regla para que el `usuario kevin pueda acceder a todo` y `el usaurio suso solo puede acceder a su home de usuario`.

- Comprobación del usuario `suso`

```console
roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): suso
331 ContraseÃ±a necesaria para suso
Password:
230 Usuario suso conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
-rw-rw-r--   1 suso     suso           22 Jan 13 11:33 descarga.txt
-rw-r--r--   1 suso     suso         8980 Jan 12 10:19 examples.desktop
-rw-rw-r--   1 suso     suso           20 Jan 13 11:32 subido.txt
226 Transferencia completada
ftp> cd /
250 Comando 'CWD' exitoso
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
-rw-rw-r--   1 suso     suso           22 Jan 13 11:33 descarga.txt
-rw-r--r--   1 suso     suso         8980 Jan 12 10:19 examples.desktop
-rw-rw-r--   1 suso     suso           20 Jan 13 11:32 subido.txt
226 Transferencia completada
ftp>
```

- Comprobación usuario `kevin`

```console
roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): kevin
331 ContraseÃ±a necesaria para kevin
Password:
230 Usuario kevin conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Descargas
-rw-rw-r--   1 kevin    kevin          22 Jan 13 11:28 descarga.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Documentos
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Escritorio
-rw-r--r--   1 kevin    kevin        8980 Jan 12 10:19 examples.desktop
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Im??genes
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 M??sica
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 Plantillas
-rw-r--r--   1 kevin    kevin           0 Jan 13 12:20 proftpddescarga.txt
-rw-r--r--   1 kevin    kevin           0 Jan 13 12:21 proftpsubida.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 P??blico
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp1.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp2.txt
-rw-rw-r--   1 kevin    kevin           0 Jan 13 11:44 scp3.txt
-rw-rw-r--   1 kevin    kevin          20 Jan 13 11:28 subido.txt
drwxr-xr-x   2 kevin    kevin        4096 Jan 13 11:39 V??deos
226 Transferencia completada
ftp> cd /
250 Comando 'CWD' exitoso
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 bin
drwxr-xr-x   3 root     root         4096 Dec 15 08:34 boot
drwxrwxr-x   2 root     root         4096 Sep 19 12:27 cdrom
drwxr-xr-x  19 root     root         3940 Jan 13 11:18 dev
drwxr-xr-x 137 root     root        12288 Jan 13 11:18 etc
drwxr-xr-x   5 root     root         4096 Jan 12 10:19 home
lrwxrwxrwx   1 root     root           33 Dec 15 08:33 initrd.img -> boot/initrd.img-4.4.0-104-generic
lrwxrwxrwx   1 root     root           33 Dec 14 08:21 initrd.img.old -> boot/initrd.img-4.4.0-103-generic
drwxr-xr-x  22 root     root         4096 Sep 19 12:29 lib
drwxr-xr-x   2 root     root         4096 Dec 14 08:18 lib64
drwx------   2 root     root        16384 Sep 19 12:25 lost+found
drwxr-xr-x   3 root     root         4096 Sep 19 15:01 media
drwxr-xr-x   2 root     root         4096 Apr 20  2016 mnt
drwxr-xr-x   3 root     root         4096 Sep 19 15:02 opt
dr-xr-xr-x 186 root     root            0 Jan 13 11:17 proc
drwx------   6 root     root         4096 Jan 13 11:48 root
drwxr-xr-x  30 root     root          980 Jan 13 12:31 run
drwxr-xr-x   2 root     root        12288 Dec 14 08:20 sbin
drwxr-xr-x   2 root     root         4096 Apr 19  2016 snap
drwxr-xr-x   3 root     root         4096 Jan 12 10:14 srv
dr-xr-xr-x  13 root     root            0 Jan 13 11:50 sys
drwxrwxrwt  10 root     root         4096 Jan 13 12:17 tmp
drwxr-xr-x  11 root     root         4096 Apr 20  2016 usr
drwxr-xr-x  16 root     root         4096 Dec 19 13:57 var
lrwxrwxrwx   1 root     root           30 Dec 15 08:33 vmlinuz -> boot/vmlinuz-4.4.0-104-generic
lrwxrwxrwx   1 root     root           30 Dec 14 08:21 vmlinuz.old -> boot/vmlinuz-4.4.0-103-generic
-rw-r--r--   1 root     root         2084 Dec 19 13:57 webmin-setup.out
226 Transferencia completada
ftp>
```

- Vamos a subir y descargar un fichero desde el equipo cliente al servidor con el usuario suso.

```console

roberto@clienterob:~$ ftp ftp.miempresa.edu
Connected to miempresa.edu.
220 ProFTPD 1.3.5a Server (Debian) [::ffff:172.18.22.1]
Name (ftp.miempresa.edu:roberto): suso
331 ContraseÃ±a necesaria para suso
Password:
230 Usuario suso conectado
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> put proftpddescarga.txt
local: proftpddescarga.txt remote: proftpddescarga.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpddescarga.txt
226 Transferencia completada
ftp> put proftpsubida.txt
local: proftpsubida.txt remote: proftpsubida.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpsubida.txt
226 Transferencia completada
ftp> ls
200 Comando PORT exitoso
150 Abriendo ASCII modo conexiÃ³n de datos para file list
-rw-rw-r--   1 suso     suso           22 Jan 13 11:33 descarga.txt
-rw-r--r--   1 suso     suso         8980 Jan 12 10:19 examples.desktop
-rw-r--r--   1 suso     suso            0 Jan 13 12:38 proftpddescarga.txt
-rw-r--r--   1 suso     suso            0 Jan 13 12:38 proftpsubida.txt
-rw-rw-r--   1 suso     suso           20 Jan 13 11:32 subido.txt
226 Transferencia completada
ftp> get proftpddescarga.txt
local: proftpddescarga.txt remote: proftpddescarga.txt
200 Comando PORT exitoso
150 Abriendo BINARY modo conexiÃ³n de datos para proftpddescarga.txt
226 Transferencia completada
ftp>
```

## 2. Crear dos usuarios llamado kevin y suso

Solo tenemos que crear dos usuarios con el comando `useradd "nombre-Usuario"`.

```console

roberto@serverob:~$ sudo adduser kevin
Añadiendo el usuario `kevin' ...
Añadiendo el nuevo grupo `kevin' (1001) ...
Añadiendo el nuevo usuario `kevin' (1001) con grupo `kevin' ...
Creando el directorio personal `/home/kevin' ...
Copiando los ficheros desde `/etc/skel' ...
Introduzca la nueva contraseña de UNIX:
Vuelva a escribir la nueva contraseña de UNIX:
passwd: contraseña actualizada correctamente
Cambiando la información de usuario para kevin
Introduzca el nuevo valor, o presione INTRO para el predeterminado
	Nombre completo []: kevin
	Número de habitación []:
	Teléfono del trabajo []:
	Teléfono de casa []:
	Otro []:
¿Es correcta la información? [S/n] s
roberto@serverob:~$ sudo adduser suso
Añadiendo el usuario `suso' ...
Añadiendo el nuevo grupo `suso' (1002) ...
Añadiendo el nuevo usuario `suso' (1002) con grupo `suso' ...
Creando el directorio personal `/home/suso' ...
Copiando los ficheros desde `/etc/skel' ...
Introduzca la nueva contraseña de UNIX:
Vuelva a escribir la nueva contraseña de UNIX:
passwd: contraseña actualizada correctamente
Cambiando la información de usuario para suso
Introduzca el nuevo valor, o presione INTRO para el predeterminado
	Nombre completo []: suso
	Número de habitación []:
	Teléfono del trabajo []:
	Teléfono de casa []:
	Otro []:
¿Es correcta la información? [S/n] s
roberto@serverob:~$

```

### 2.1 Establecemos los siguiente privilegios para los usuarios.

Un usuario tiene que tener privilegio de `Administrador` y el otro usuario como `Estándar`.

Tenemos que ir a `Cuentas de usuario`

- Kevin: `Administrador`

![](img/002.png)

- Suso: `Estándar`

![](img/003.png)

## 3. Tenemos que instalar el servicio ssh

Tenemos que instalar el servicio ssh.

```console

roberto@serverob:~$ sudo apt install ssh
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  linux-headers-4.4.0-21 linux-headers-4.4.0-21-generic
  linux-image-4.4.0-21-generic linux-image-extra-4.4.0-21-generic
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  ncurses-term openssh-client openssh-server openssh-sftp-server ssh-import-id
Paquetes sugeridos:
  ssh-askpass libpam-ssh keychain monkeysphere rssh molly-guard
Se instalarán los siguientes paquetes NUEVOS:
  ncurses-term openssh-server openssh-sftp-server ssh ssh-import-id
Se actualizarán los siguientes paquetes:
  openssh-client
1 actualizados, 5 nuevos se instalarán, 0 para eliminar y 385 no actualizados.
Se necesita descargar 1.230 kB de archivos.
Se utilizarán 5.244 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 openssh-client amd64 1:7.2p2-4ubuntu2.2 [587 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 openssh-sftp-server amd64 1:7.2p2-4ubuntu2.2 [38,7 kB]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 openssh-server amd64 1:7.2p2-4ubuntu2.2 [338 kB]
Des:4 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 ssh all 1:7.2p2-4ubuntu2.2 [7.076 B]
Des:5 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 ncurses-term all 6.0+20160213-1ubuntu1 [249 kB]
Des:6 http://es.archive.ubuntu.com/ubuntu xenial/main amd64 ssh-import-id all 5.5-0ubuntu1 [10,2 kB]
Descargados 1.230 kB en 2s (506 kB/s)
Preconfigurando paquetes ...
(Leyendo la base de datos ... 267353 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../openssh-client_1%3a7.2p2-4ubuntu2.2_amd64.deb ...
Desempaquetando openssh-client (1:7.2p2-4ubuntu2.2) sobre (1:7.2p2-4ubuntu2.1) ...
Seleccionando el paquete openssh-sftp-server previamente no seleccionado.
Preparando para desempaquetar .../openssh-sftp-server_1%3a7.2p2-4ubuntu2.2_amd64.deb ...
Desempaquetando openssh-sftp-server (1:7.2p2-4ubuntu2.2) ...
Seleccionando el paquete openssh-server previamente no seleccionado.
Preparando para desempaquetar .../openssh-server_1%3a7.2p2-4ubuntu2.2_amd64.deb ...
Desempaquetando openssh-server (1:7.2p2-4ubuntu2.2) ...
Seleccionando el paquete ssh previamente no seleccionado.
Preparando para desempaquetar .../ssh_1%3a7.2p2-4ubuntu2.2_all.deb ...
Desempaquetando ssh (1:7.2p2-4ubuntu2.2) ...
Seleccionando el paquete ncurses-term previamente no seleccionado.
Preparando para desempaquetar .../ncurses-term_6.0+20160213-1ubuntu1_all.deb ...
Desempaquetando ncurses-term (6.0+20160213-1ubuntu1) ...
Seleccionando el paquete ssh-import-id previamente no seleccionado.
Preparando para desempaquetar .../ssh-import-id_5.5-0ubuntu1_all.deb ...
Desempaquetando ssh-import-id (5.5-0ubuntu1) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Configurando openssh-client (1:7.2p2-4ubuntu2.2) ...
Configurando openssh-sftp-server (1:7.2p2-4ubuntu2.2) ...
Configurando openssh-server (1:7.2p2-4ubuntu2.2) ...
Creating SSH2 RSA key; this may take some time ...
2048 SHA256:m9FMig6mZuuXE47oYL5Z6Ch9bERi9o7ZS088ZJ5iNfo root@serverob (RSA)
Creating SSH2 DSA key; this may take some time ...
1024 SHA256:fIiaa/KUBX5AnEecoNg/wCjONVb3lo2x5QH0QipbUbg root@serverob (DSA)
Creating SSH2 ECDSA key; this may take some time ...
256 SHA256:0+VFKiIShDegREsG+fzi3p7y1jVpas7mBh6ZIFuSGXA root@serverob (ECDSA)
Creating SSH2 ED25519 key; this may take some time ...
256 SHA256:B30qOnWYmln1BO22XWgoaF2l7QQN3KB3Ae1aTsDCH44 root@serverob (ED25519)
Configurando ssh (1:7.2p2-4ubuntu2.2) ...
Configurando ncurses-term (6.0+20160213-1ubuntu1) ...
Configurando ssh-import-id (5.5-0ubuntu1) ...
Procesando disparadores para systemd (229-4ubuntu10) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...
```

Ya tenemos instalado el servicio.

### 3.1 Modificar fichero /etc/ssh/sshd_config

Tenemos que ir a la siguiente ruta `/etc/ssh/sshd_config`

```console
roberto@serverob:~$ sudo nano /etc/ssh/
moduli                    sshd_config               ssh_host_dsa_key.pub      ssh_host_ecdsa_key.pub    ssh_host_ed25519_key.pub  ssh_host_rsa_key.pub      
ssh_config                ssh_host_dsa_key          ssh_host_ecdsa_key        ssh_host_ed25519_key      ssh_host_rsa_key          ssh_import_id             
roberto@serverob:~$ sudo nano /etc/ssh/sshd_config
```

- Tenemos que ver si `X11Forwarding yes`

```console
roberto@serverob:~$ sudo cat /etc/ssh/sshd_config | grep X11
X11Forwarding yes
X11DisplayOffset 10
roberto@serverob:~$
```
### 3.2 Conectarnos desde un Equipo Cliente ubuntu al server ftp Ubuntu mediante ssh_host_dsa_key

Solo tenemos que escribir en la terminal el siguiente comando `ssh -X kevin@172.18.22.1`

```console
roberto@clienterob:~$ ssh -X kevin@172.18.22.1
kevin@172.18.22.1's password:
Welcome to Ubuntu 16.04 LTS (GNU/Linux 4.4.0-104-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

Pueden actualizarse 390 paquetes.
25 actualizaciones son de seguridad.

Last login: Fri Jan 12 10:35:29 2018 from 172.18.22.3
/usr/bin/xauth:  file /home/kevin/.Xauthority does not exist
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

kevin@serverob:~$ whoami
kevin
kevin@serverob:~$ hostname
serverob
kevin@serverob:~$
```

Comprobamos con una aplicación, en mi caso `gedit`.

![](img/004.png)

### 3.3 Acceder desde el cliente, mediante sftp.

Lo primero que tenemos que realizar en el equipo cliente es crear dos ficheros. En mi caso los llamaré `subida.txt y descarga.txt`.

```console
roberto@clienterob:~$ echo "hola fichero subido" > subido.txt
roberto@clienterob:~$ echo "hola fichero descarga" > descarga.txt
roberto@clienterob:~$ ls
Descargas     Documentos  examples.desktop  Música      Público     Vídeos
descarga.txt  Escritorio  Imágenes          Plantillas  subido.txt
roberto@clienterob:~$
```

#### 3.3.1 Conectar al SFTP

Solo tenemos que escribir la terminal y escribir el siguiente comando.

- `sftp usuario@ip-server`

```console
roberto@clienterob:~$ sftp kevin@172.18.22.1
kevin@172.18.22.1's password:
Connected to 172.18.22.1.
sftp> dir
examples.desktop    
sftp> ls
examples.desktop    
sftp> help
Available commands:
bye                                Quit sftp
cd path                            Change remote directory to 'path'
chgrp grp path                     Change group of file 'path' to 'grp'
chmod mode path                    Change permissions of file 'path' to 'mode'
chown own path                     Change owner of file 'path' to 'own'
df [-hi] [path]                    Display statistics for current directory or
                                   filesystem containing 'path'
exit                               Quit sftp
get [-afPpRr] remote [local]       Download file
reget [-fPpRr] remote [local]      Resume download file
reput [-fPpRr] [local] remote      Resume upload file
help                               Display this help text
lcd path                           Change local directory to 'path'
lls [ls-options [path]]            Display local directory listing
lmkdir path                        Create local directory
ln [-s] oldpath newpath            Link remote file (-s for symlink)
lpwd                               Print local working directory
ls [-1afhlnrSt] [path]             Display remote directory listing
lumask umask                       Set local umask to 'umask'
mkdir path                         Create remote directory
progress                           Toggle display of progress meter
put [-afPpRr] local [remote]       Upload file
pwd                                Display remote working directory
quit                               Quit sftp
rename oldpath newpath             Rename remote file
rm path                            Delete remote file
rmdir path                         Remove remote directory
symlink oldpath newpath            Symlink remote file
version                            Show SFTP version
!command                           Execute 'command' in local shell
!                                  Escape to local shell
?                                  Synonym for help
sftp> lpwd
Local working directory: /home/roberto
sftp> lls
Descargas     Documentos  examples.desktop  Música	Público     Vídeos
descarga.txt  Escritorio  Imágenes	    Plantillas	subido.txt
sftp>
```

#### 3.3.2 Subir y descargar fichero desde equipo cliente al usuario kevin del servidor.

Solo tenemos que abrir una terminal.

- Con el usuario Kevin

```console
roberto@clienterob:~$ sftp kevin@172.18.22.1
kevin@172.18.22.1's password:
Permission denied, please try again.
kevin@172.18.22.1's password:
Connected to 172.18.22.1.
sftp> put subido.txt
Uploading subido.txt to /home/kevin/subido.txt
subido.txt                                    100%   20     0.0KB/s   00:00    
sftp> put descarga.txt
Uploading descarga.txt to /home/kevin/descarga.txt
descarga.txt                                  100%   22     0.0KB/s   00:00    
sftp> ls
descarga.txt        examples.desktop    subido.txt          
sftp> get subido.txt
Fetching /home/kevin/subido.txt to subido.txt
/home/kevin/subido.txt                        100%   20     0.0KB/s   00:00    
sftp> lls
Descargas   Escritorio	      Imágenes	Plantillas  Vídeos
Documentos  examples.desktop  Música	Público
sftp> get subido.txt
Fetching /home/kevin/subido.txt to subido.txt
/home/kevin/subido.txt                        100%   20     0.0KB/s   00:00    
sftp> get descarga.txt
Fetching /home/kevin/descarga.txt to descarga.txt
/home/kevin/descarga.txt                      100%   22     0.0KB/s   00:00    
sftp> lls
Descargas     Documentos  examples.desktop  Música	Público     Vídeos
descarga.txt  Escritorio  Imágenes	    Plantillas	subido.txt
sftp>
```
- Con el usuario Suso

```console
roberto@clienterob:~$ sftp suso@172.18.22.1
suso@172.18.22.1's password:
Connected to 172.18.22.1.
sftp> ls
examples.desktop    subido.txt          
sftp> put subido.txt
Uploading subido.txt to /home/suso/subido.txt
subido.txt                                    100%   20     0.0KB/s   00:00    
sftp> c
cd     chdir  chgrp  chmod  chown  
sftp> put descarga.txt
Uploading descarga.txt to /home/suso/descarga.txt
descarga.txt                                  100%   22     0.0KB/s   00:00    
sftp> lls
Descargas     Documentos  examples.desktop  Música	Público     Vídeos
descarga.txt  Escritorio  Imágenes	    Plantillas	subido.txt
sftp> ls
descarga.txt        examples.desktop    subido.txt          
sftp> lls
Descargas   Escritorio	      Imágenes	Plantillas  subido.txt
Documentos  examples.desktop  Música	Público     Vídeos
sftp> get descarga.txt
Fetching /home/suso/descarga.txt to descarga.txt
/home/suso/descarga.txt                       100%   22     0.0KB/s   00:00    
sftp> lls
Descargas     Documentos  examples.desktop  Música	Público     Vídeos
descarga.txt  Escritorio  Imágenes	    Plantillas	subido.txt
sftp>
```

### 3.4 Utilizando el comando SPC

Primero creamos unos ficheros llamados `scp1.txt, scp2.txt, scp3.txt`

- Para subir el fichero mediante scp tiene la siguiente manera:

- `scp /ruta/al/archivo-origen usuario@ordenador:/ruta/al/directorio-destino/`

- Comprobamos pasar un fichero mediante scp al usuario `kevin y suso`


```console
kevin@serverob:~$ sudo scp scp?.txt kevin@172.18.22.1:/tmp
kevin@172.18.22.1's password:
scp1.txt                                      100%    0     0.0KB/s   00:00    
scp2.txt                                      100%    0     0.0KB/s   00:00    
scp3.txt                                      100%    0     0.0KB/s   00:00    
kevin@serverob:~$ sudo scp scp?.txt suso@172.18.22.1:/tmp
suso@172.18.22.1's password:
scp: /tmp/scp1.txt: Permission denied
scp: /tmp/scp2.txt: Permission denied
scp: /tmp/scp3.txt: Permission denied
kevin@serverob:~$ ls -l /tmp/
total 8
-rw------- 1 kevin kevin    0 ene 13 11:39 config-err-76NOz2
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp1.txt
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp2.txt
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:49 scp3.txt
drwx------ 3 root  root  4096 ene 13 11:18 systemd-private-feb28b88fc3246358c0616864e7abd13-colord.service-jSgaPc
drwx------ 3 root  root  4096 ene 13 11:18 systemd-private-feb28b88fc3246358c0616864e7abd13-rtkit-daemon.service-gYy6tx
-rw-rw-r-- 1 kevin kevin    0 ene 13 11:39 unity_support_test.1
kevin@serverob:~$
```
