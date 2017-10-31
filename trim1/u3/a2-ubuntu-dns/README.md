# Ubuntu Server DNS

- [Instalación y configuración DNS bind9 en Ubuntu](#1)

    - [Configuración de su tarjeta de red](#2)
    - [Indicar a Linux que el servidor DNS es él mismo (/etc/resolv.conf) en el Servidor](#3)
    - [Configurar servidor como caché DNS (/etc/bind/named.conf.options) con reenviadores de DNS con DNS públicos (p.e.: 8.8.8.8 y 80.58.61.250)](#4)
    - [Comprobar resolución de nombres externos, tanto desde el servidor como desde un cliente al que le preste servicio DNS.](#5)
    - [Configurar como DNS maestro instalando un dominio ficticio (tu empresa virtual) y añadiendo configuración para búsquedas de zona directa y zona inversa (/etc/bind/named.conf.local)](#6)

        - [Zona Directa](#7)
        - [Zona Inversa](#8)

    - [Comprobar que se resuelven los nombres desde la consola del servidor.](#9)
    - [Comprobar que se resuelven los nombres desde la consola del cliente.](#10)


- [Configuración de Servidor DNS-Slave](#11)

    - [Configurar el fichero `/etc/bind/named.conf.local`](#12)
    - [Comprobar resolución de Nombre en el Equipo Cliente](#13)

![img](img/000.png)

Trabajo realizado por:

Kevin Hernández García
Roberto Hernández Sanabria


## Realizar la instalación y configuración de un servidor DNS bind9 en una máquina Linux.<a name="1"></a>

Para la instalación del servicio o demonio DNS bind9, debemos escribir el siguiente comando.

```console

roberto@serverob:~$ sudo apt install bind9
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  libirs-export141 libisccfg-export140
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  bind9-host bind9utils dnsutils libbind9-140 libdns162 libirs141 libisc160
  libisccc140 libisccfg140 liblwres141
Paquetes sugeridos:
  bind9-doc rblcheck
Se instalarán los siguientes paquetes NUEVOS:
  bind9 bind9utils libirs141
Se actualizarán los siguientes paquetes:
  bind9-host dnsutils libbind9-140 libdns162 libisc160 libisccc140
  libisccfg140 liblwres141
8 actualizados, 3 nuevos se instalarán, 0 para eliminar y 557 no actualizados.
Se necesita descargar 1.929 kB de archivos.
Se utilizarán 2.962 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 dnsutils amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [89,0 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 bind9-host amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [38,4 kB]
Des:3 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libisc160 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [215 kB]
Des:4 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libdns162 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [882 kB]
Des:5 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libisccc140 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [16,3 kB]
Des:6 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libisccfg140 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [40,4 kB]
Des:7 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 liblwres141 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [33,7 kB]
Des:8 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libbind9-140 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [23,6 kB]
Des:9 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libirs141 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [18,0 kB]
Des:10 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 bind9utils amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [200 kB]
Des:11 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 bind9 amd64 1:9.10.3.dfsg.P4-8ubuntu1.8 [372 kB]
Descargados 1.929 kB en 21s (90,5 kB/s)
Preconfigurando paquetes ...
(Leyendo la base de datos ... 175790 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../dnsutils_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando dnsutils (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../bind9-host_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando bind9-host (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../libisc160_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libisc160:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../libdns162_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libdns162:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../libisccc140_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libisccc140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../libisccfg140_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libisccfg140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../liblwres141_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando liblwres141:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Preparando para desempaquetar .../libbind9-140_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libbind9-140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) sobre (1:9.10.3.dfsg.P4-8) ...
Seleccionando el paquete libirs141:amd64 previamente no seleccionado.
Preparando para desempaquetar .../libirs141_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando libirs141:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Seleccionando el paquete bind9utils previamente no seleccionado.
Preparando para desempaquetar .../bind9utils_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando bind9utils (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Seleccionando el paquete bind9 previamente no seleccionado.
Preparando para desempaquetar .../bind9_1%3a9.10.3.dfsg.P4-8ubuntu1.8_amd64.deb ...
Desempaquetando bind9 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...
Configurando libisc160:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando libdns162:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando libisccc140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando libisccfg140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando libbind9-140:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando liblwres141:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando bind9-host (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando dnsutils (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando libirs141:amd64 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando bind9utils (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Configurando bind9 (1:9.10.3.dfsg.P4-8ubuntu1.8) ...
Añadiendo el grupo `bind' (GID 130) ...
Hecho.
Añadiendo el usuario del sistema `bind' (UID 122) ...
Añadiendo un nuevo usuario `bind' (UID 122) con grupo `bind' ...
No se crea el directorio personal `/var/cache/bind'.
wrote key file "/etc/bind/rndc.key"
#
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Procesando disparadores para ureadahead (0.100.0-19) ...
Procesando disparadores para systemd (229-4ubuntu4) ...
Procesando disparadores para ufw (0.35-0ubuntu2) ...

```
### Configuración de su tarjeta de red<a name="2"></a>

```console

roberto@serverob:~$ sudo cat /etc/network/interfaces
[sudo] password for roberto:
# interfaces(5) file used by ifup(8) and ifdown(8)
auto lo
iface lo inet loopback

#Tarjeta de red enp0s3

auto enp0s3
iface enp0s3 inet static


	address 172.18.22.1
	gateway 172.18.0.1
	netmask	255.255.0.0
	dns-domain skynet.edu
	dns-nameservers 172.18.22.1


```


### Indicar a Linux que el servidor DNS es él mismo (/etc/resolv.conf) en el Servidor<a name="3"></a>


```console

roberto@serverob:~$ sudo nano /etc/resolv.conf
roberto@serverob:~$ sudo cat /etc/resolv.conf
# Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
#     DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 172.18.22.1

```

En caso de problema con el resolv.conf, tenemos una recomendación es quitar el network-manager. Configurar todos los ficheros de configuración de network en la siguiente ruta `/etc/network/interfaces`. Es una opción para que no se cambie el fichero de `resolv.conf`.

```console
roberto@serverob:~$ sudo systemctl stop networking.service
roberto@serverob:~$ sudo apt purge network-manager
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  ethtool libx86-1 plainbox-secure-policy pm-utils pyotherside
  python3-checkbox-support python3-guacamole python3-jinja2 python3-padme
  python3-plainbox python3-pyparsing python3-xlsxwriter
  qml-module-io-thp-pyotherside qmlscene qtdeclarative5-dev-tools vbetool
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  libnma-common libnma0
Los siguientes paquetes se ELIMINARÁN:
  checkbox-converged* checkbox-gui* network-manager* network-manager-gnome*
  plainbox-provider-checkbox* plainbox-provider-resource-generic* ubuntu-desktop*
Se actualizarán los siguientes paquetes:
  libnma-common libnma0
2 actualizados, 0 nuevos se instalarán, 7 para eliminar y 553 no actualizados.
Se necesita descargar 72,1 kB de archivos.
Se liberarán 15,2 MB después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libnma0 amd64 1.2.6-0ubuntu0.16.04.3 [66,5 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libnma-common all 1.2.6-0ubuntu0.16.04.3 [5.650 B]
Descargados 72,1 kB en 0s (161 kB/s)
(Leyendo la base de datos ... 175894 ficheros o directorios instalados actualmente.)
Desinstalando ubuntu-desktop (1.361) ...
Desinstalando checkbox-gui (1.2.4-0ubuntu1) ...
Desinstalando checkbox-converged (1.2.4-0ubuntu1) ...
Desinstalando network-manager-gnome (1.1.93-1ubuntu1) ...
Purgando ficheros de configuración de network-manager-gnome (1.1.93-1ubuntu1) ...
Desinstalando plainbox-provider-checkbox (0.25-1) ...
Desinstalando plainbox-provider-resource-generic (0.23-1) ...
Desinstalando network-manager (1.1.93-0ubuntu4) ...
Purgando ficheros de configuración de network-manager (1.1.93-0ubuntu4) ...
dpkg: aviso: al desinstalar network-manager, el directorio «/etc/NetworkManager/system-connections» no está vacío, por lo que no se borra
Procesando disparadores para gnome-menus (3.13.3-6ubuntu3) ...
Procesando disparadores para desktop-file-utils (0.22-1ubuntu5) ...
Procesando disparadores para bamfdaemon (0.5.3~bzr0+16.04.20160415-0ubuntu1) ...
Rebuilding /usr/share/applications/bamf-2.index...
Procesando disparadores para mime-support (3.59ubuntu1) ...
Procesando disparadores para hicolor-icon-theme (0.15-0ubuntu1) ...
Procesando disparadores para libglib2.0-0:amd64 (2.48.0-1ubuntu4) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para gconf2 (3.2.6-3ubuntu6) ...
Procesando disparadores para dbus (1.10.6-1ubuntu3) ...
(Leyendo la base de datos ... 175398 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../libnma0_1.2.6-0ubuntu0.16.04.3_amd64.deb ...
Desempaquetando libnma0:amd64 (1.2.6-0ubuntu0.16.04.3) sobre (1.1.93-1ubuntu1) ...
Preparando para desempaquetar .../libnma-common_1.2.6-0ubuntu0.16.04.3_all.deb ...
Desempaquetando libnma-common (1.2.6-0ubuntu0.16.04.3) sobre (1.1.93-1ubuntu1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Configurando libnma-common (1.2.6-0ubuntu0.16.04.3) ...
Configurando libnma0:amd64 (1.2.6-0ubuntu0.16.04.3) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...

```
- Reiniciamos el sistema operativo Ubuntu para comprobar que no se cambia el resolv.conf

### Configurar servidor como caché DNS (/etc/bind/named.conf.options) con reenviadores de DNS con DNS públicos (p.e.: 8.8.8.8 y 80.58.61.250).<a name="4"></a>

Primero realizamos una copia de seguridad del fichero por defecto.

```console

roberto@serverob:~$ sudo cp /etc/bind/named.conf.options /etc/bind/named.conf.options.000

```

- Modificamos el fichero `named.conf.options`, solo tenemos que descomentar `forwarders` y dentro escribir los DNS.

```console

roberto@serverob:~$ sudo cat /etc/bind/named.conf.options
options {
	directory "/var/cache/bind";

	// If there is a firewall between you and nameservers you want
	// to talk to, you may need to fix the firewall to allow multiple
	// ports to talk.  See http://www.kb.cert.org/vuls/id/800113

	// If your ISP provided one or more IP addresses for stable
	// nameservers, you probably want to use them as forwarders.  
	// Uncomment the following block, and insert the addresses replacing
	// the all-0's placeholder.

	 forwarders {
		8.8.8.8;
		80.58.61.250;
	 };

	//========================================================================
	// If BIND logs error messages about the root key being expired,
	// you will need to update your keys.  See https://www.isc.org/bind-keys
	//========================================================================
	dnssec-validation auto;

	auth-nxdomain no;    # conform to RFC1035
	listen-on-v6 { any; };
};

```

- Tenemos que reiniciar el servicios de bind9


```console
roberto@serverob:~$ sudo systemctl restart bind9
roberto@serverob:~$ sudo systemctl status bind9
● bind9.service - BIND Domain Name Server
   Loaded: loaded (/lib/systemd/system/bind9.service; enabled; vendor preset: en
  Drop-In: /run/systemd/generator/bind9.service.d
           └─50-insserv.conf-$named.conf
   Active: active (running) since vie 2017-10-27 10:16:47 WEST; 4s ago
     Docs: man:named(8)
  Process: 2276 ExecStop=/usr/sbin/rndc stop (code=exited, status=0/SUCCESS)
 Main PID: 2280 (named)
    Tasks: 4 (limit: 512)
   CGroup: /system.slice/bind9.service
           └─2280 /usr/sbin/named -f -u bind

oct 27 10:16:47 serverob named[2280]: configuring command channel from '/etc/bin
oct 27 10:16:47 serverob named[2280]: command channel listening on ::1#953
oct 27 10:16:47 serverob named[2280]: managed-keys-zone: journal file is out of
oct 27 10:16:47 serverob named[2280]: managed-keys-zone: loaded serial 3
oct 27 10:16:47 serverob named[2280]: zone 0.in-addr.arpa/IN: loaded serial 1
oct 27 10:16:47 serverob named[2280]: zone 127.in-addr.arpa/IN: loaded serial 1
oct 27 10:16:47 serverob named[2280]: zone localhost/IN: loaded serial 2
oct 27 10:16:47 serverob named[2280]: zone 255.in-addr.arpa/IN: loaded serial 1
oct 27 10:16:47 serverob named[2280]: all zones loaded
oct 27 10:16:47 serverob named[2280]: running
roberto@serverob:~$


```

### Comprobar resolución de nombres externos, tanto desde el servidor como desde un cliente al que le preste servicio DNS.<a name="5"></a>

Realizamos una comprobación desde un servidor con el comando `nslookup`

```console
roberto@serverob:~$ nslookup www.google.es
Server:		172.18.22.1
Address:	172.18.22.1#53

Non-authoritative answer:
Name:	www.google.es
Address: 216.58.210.195

roberto@serverob:~$ nslookup www.facebook.es
Server:		172.18.22.1
Address:	172.18.22.1#53

Non-authoritative answer:
www.facebook.es	canonical name = www.facebook.com.
www.facebook.com	canonical name = star-mini.c10r.facebook.com.
Name:	star-mini.c10r.facebook.com
Address: 157.240.1.35

roberto@serverob:~$


```

Realizamos una comprobación desde un equipo cliente con el comando `nslookup`.

- Importante cambiar el resolv.conf en el equipo cliente.


```console

roberto@clienterob:~$ sudo nano /etc/resolv.conf
roberto@clienterob:~$ sudo cat /etc/resolv.conf
# Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
#     DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 172.18.22.1

roberto@clienterob:~$ nslookup www.google.es
Server:		172.18.22.1
Address:	172.18.22.1#53

Non-authoritative answer:
Name:	www.google.es
Address: 216.58.210.195

roberto@clienterob:~$ nslookup www.facebook.es
Server:		172.18.22.1
Address:	172.18.22.1#53

Non-authoritative answer:
www.facebook.es	canonical name = www.facebook.com.
www.facebook.com	canonical name = star-mini.c10r.facebook.com.
Name:	star-mini.c10r.facebook.com
Address: 157.240.1.35


```

En caso de problema con el resolv.conf, tenemos una recomendación es quitar el network-manager. Configurar todos los ficheros de configuración de network en la siguiente ruta `/etc/network/interfaces`. Es una opción para que no se cambie el fichero de `resolv.conf`


```console
roberto@clienterob:~$ sudo systemctl stop networking.service
roberto@clienterob:~$ sudo apt purge network-manager
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  ethtool libx86-1 plainbox-secure-policy pm-utils pyotherside
  python3-checkbox-support python3-guacamole python3-jinja2 python3-padme
  python3-plainbox python3-pyparsing python3-xlsxwriter
  qml-module-io-thp-pyotherside qmlscene qtdeclarative5-dev-tools vbetool
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes adicionales:
  libnma-common libnma0
Los siguientes paquetes se ELIMINARÁN:
  checkbox-converged* checkbox-gui* network-manager* network-manager-gnome*
  plainbox-provider-checkbox* plainbox-provider-resource-generic* ubuntu-desktop*
Se actualizarán los siguientes paquetes:
  libnma-common libnma0
2 actualizados, 0 nuevos se instalarán, 7 para eliminar y 553 no actualizados.
Se necesita descargar 72,1 kB de archivos.
Se liberarán 15,2 MB después de esta operación.
¿Desea continuar? [S/n] s
Des:1 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libnma0 amd64 1.2.6-0ubuntu0.16.04.3 [66,5 kB]
Des:2 http://es.archive.ubuntu.com/ubuntu xenial-updates/main amd64 libnma-common all 1.2.6-0ubuntu0.16.04.3 [5.650 B]
Descargados 72,1 kB en 0s (161 kB/s)
(Leyendo la base de datos ... 175894 ficheros o directorios instalados actualmente.)
Desinstalando ubuntu-desktop (1.361) ...
Desinstalando checkbox-gui (1.2.4-0ubuntu1) ...
Desinstalando checkbox-converged (1.2.4-0ubuntu1) ...
Desinstalando network-manager-gnome (1.1.93-1ubuntu1) ...
Purgando ficheros de configuración de network-manager-gnome (1.1.93-1ubuntu1) ...
Desinstalando plainbox-provider-checkbox (0.25-1) ...
Desinstalando plainbox-provider-resource-generic (0.23-1) ...
Desinstalando network-manager (1.1.93-0ubuntu4) ...
Purgando ficheros de configuración de network-manager (1.1.93-0ubuntu4) ...
dpkg: aviso: al desinstalar network-manager, el directorio «/etc/NetworkManager/system-connections» no está vacío, por lo que no se borra
Procesando disparadores para gnome-menus (3.13.3-6ubuntu3) ...
Procesando disparadores para desktop-file-utils (0.22-1ubuntu5) ...
Procesando disparadores para bamfdaemon (0.5.3~bzr0+16.04.20160415-0ubuntu1) ...
Rebuilding /usr/share/applications/bamf-2.index...
Procesando disparadores para mime-support (3.59ubuntu1) ...
Procesando disparadores para hicolor-icon-theme (0.15-0ubuntu1) ...
Procesando disparadores para libglib2.0-0:amd64 (2.48.0-1ubuntu4) ...
Procesando disparadores para man-db (2.7.5-1) ...
Procesando disparadores para gconf2 (3.2.6-3ubuntu6) ...
Procesando disparadores para dbus (1.10.6-1ubuntu3) ...
(Leyendo la base de datos ... 175398 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../libnma0_1.2.6-0ubuntu0.16.04.3_amd64.deb ...
Desempaquetando libnma0:amd64 (1.2.6-0ubuntu0.16.04.3) sobre (1.1.93-1ubuntu1) ...
Preparando para desempaquetar .../libnma-common_1.2.6-0ubuntu0.16.04.3_all.deb ...
Desempaquetando libnma-common (1.2.6-0ubuntu0.16.04.3) sobre (1.1.93-1ubuntu1) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...
Configurando libnma-common (1.2.6-0ubuntu0.16.04.3) ...
Configurando libnma0:amd64 (1.2.6-0ubuntu0.16.04.3) ...
Procesando disparadores para libc-bin (2.23-0ubuntu3) ...

```

- Reiniciamos el sistema operativo ubuntu y ya no tiene porque cambiarse el `resolv.conf`.

### Configurar como DNS maestro instalando un dominio ficticio (tu empresa virtual) y añadiendo configuración para búsquedas de zona directa y zona inversa (/etc/bind/named.conf.local)<a name="6"></a>

Configuramos el fichero `named.conf.local` para añadir las zonas directa y zona inversa.

```console

roberto@serverob:~$ sudo nano /etc/bind/named.conf.local
sudo cat /etc/bind/named.conf.local
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

# Archivo para búsquedas inversas

zone "18.172.in-addr.arpa" {
	type master;
	file "/etc/bind/db.172";
};


```

- Debemos crear los ficheros zona directa `db.skynet` y zona inversa `db.172`.

```console
roberto@serverob:~$ sudo touch /etc/bind/db.172
roberto@serverob:~$ sudo touch /etc/bind/db.skynet
roberto@serverob:~$ sudo ls -l /etc/bind/
total 52
-rw-r--r-- 1 root root 3954 sep 15 16:20 bind.keys
-rw-r--r-- 1 root root  237 sep 15 16:20 db.0
-rw-r--r-- 1 root root  271 oct 27 23:18 db.127
-rw-r--r-- 1 root bind    0 oct 27 23:23 db.172
-rw-r--r-- 1 root root  237 sep 15 16:20 db.255
-rw-r--r-- 1 root root  353 sep 15 16:20 db.empty
-rw-r--r-- 1 root bind    0 oct 27 23:17 db.local
-rw-r--r-- 1 root root 3171 sep 15 16:20 db.root
-rw-r--r-- 1 root bind    0 oct 27 23:23 db.skynet
-rw-r--r-- 1 root bind  463 sep 15 16:20 named.conf
-rw-r--r-- 1 root bind  490 sep 15 16:20 named.conf.default-zones
-rw-r--r-- 1 root bind  422 oct 27 23:19 named.conf.local
-rw-r--r-- 1 root bind  901 oct 27 10:15 named.conf.options
-rw-r--r-- 1 root bind  890 oct 27 10:09 named.conf.options.000
-rw-r----- 1 bind bind   77 oct 27 09:42 rndc.key
-rw-r--r-- 1 root root 1317 sep 15 16:20 zones.rfc1918
roberto@serverob:~$


```


#### Zona de búsqueda directa<a name="7"></a>

Ya tenemos creado el fichero en `/etc/bind/db.skynet` para la zona directa. Solo debemos añadir nuevos registros.

```console
roberto@serverob:~$ sudo nano /etc/bind/db.skynet
sudo cat /etc/bind/db.skynet

;
; BIND data file for local loopback interface
;
$TTL	604800
@	IN	SOA	 skynet.edu. root.skynet.edu. (
	2 ; Serial
	604800 ; Refresh
	86400 ; Retry
	2419200 ; Expire
	604800 ) ; Negative Cache TTL
;

@		IN	NS		skynet.edu.
@		IN	A		172.18.22.1
@		IN	MX	0	skynet.edu.
serverob	IN	A		172.18.22.1
server		IN	CNAME		serverob.skynet.edu.
printer		IN	A		172.18.22.4
clienterob	IN	A		172.18.22.3
servermail	IN	A		172.18.22.5
mail		IN	MX	0	servermail.skynet.edu.

```

#### Zona de búsqueda inversa<a name="8"></a>

Tenemos que ir al fichero de configuración `/etc/bind/db.172` este fichero lo creamos para la zona inversa.

```console

roberto@serverob:~$ sudo cat /etc/bind/db.172
;
; BIND reverse data file for local loopback interface
;
$TTL	604800
@	IN	 SOA	 skynet.edu. root.skynet.edu. (
	1 ; Serial
	604800 ; Refresh
	86400 ; Retry
	2419200 ; Expire
	604800 ) ; Negative Cache TTL
;

@		IN	NS	skynet.edu.

22.1		IN	PTR	serverob.skynet.edu.
22.3		IN	PTR	clienterob.skynet.edu.
22.5		IN	PTR	servermail.skynet.edu.
22.4		IN	PTR	printer.skynet.edu.
roberto@serverob:~$


```

### Comprobar que se resuelven los nombres desde la consola del servidor.<a name="9"></a>

```console
roberto@serverob:~$ nslookup server
Server:		172.18.22.1
Address:	172.18.22.1#53

server.skynet.edu	canonical name = serverob.skynet.edu.
Name:	serverob.skynet.edu
Address: 172.18.22.1

roberto@serverob:~$ nslookup -type=a printer
Server:		172.18.22.1
Address:	172.18.22.1#53

Name:	printer.skynet.edu
Address: 172.18.22.4

roberto@serverob:~$ nslookup -type=mx mail
Server:		172.18.22.1
Address:	172.18.22.1#53

mail.skynet.edu	mail exchanger = 0 servermail.skynet.edu.

roberto@serverob:~$ nslookup clienterob
Server:		172.18.22.1
Address:	172.18.22.1#53

Name:	clienterob.skynet.edu
Address: 172.18.22.3

roberto@serverob:~$

```

### Comprobar desde la consola del cliente que se resuelven correctamente los nombres dados de alta en el servidor (aunque en algunos casos, si se trata de direcciones ficticias, no se obtenga respuesta).<a name="10"></a>


```console

roberto@clienterob:~$ nslookup server.skynet.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

server.skynet.edu	canonical name = serverob.skynet.edu.
Name:	serverob.skynet.edu
Address: 172.18.22.1

roberto@clienterob:~$ nslookup -type=mx mail.skynet.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

mail.skynet.edu	mail exchanger = 0 servermail.skynet.edu.

roberto@clienterob:~$ nslookup printer.skynet.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

Name:	printer.skynet.edu
Address: 172.18.22.4

roberto@clienterob:~$ nslookup server.skynet.edu
Server:		172.18.22.1
Address:	172.18.22.1#53

server.skynet.edu	canonical name = serverob.skynet.edu.
Name:	serverob.skynet.edu
Address: 172.18.22.1

roberto@clienterob:~$ nslookup www.facebook.es
Server:		172.18.22.1
Address:	172.18.22.1#53

Non-authoritative answer:
www.facebook.es	canonical name = www.facebook.com.
www.facebook.com	canonical name = star-mini.c10r.facebook.com.
Name:	star-mini.c10r.facebook.com
Address: 157.240.1.35

roberto@clienterob:~$


```



## Configuración de Servidor DNS-Slave<a name="11"></a>


 Primero tenemos que cambiar el nombre al Servidor, cambiar la dirección IP del servidor y establecer una nueva dirección IP en el `resolv.conf`.

```console

roberto@serverob2:~$ hostname
serverob2
roberto@serverob2:~$ ifconfig
enp0s3    Link encap:Ethernet  direcciónHW 08:00:27:b3:59:d5  
          Direc. inet:172.18.22.2  Difus.:172.18.255.255  Másc:255.255.0.0
          Dirección inet6: fe80::a00:27ff:feb3:59d5/64 Alcance:Enlace
          ACTIVO DIFUSIÓN FUNCIONANDO MULTICAST  MTU:1500  Métrica:1
          Paquetes RX:20 errores:0 perdidos:0 overruns:0 frame:0
          Paquetes TX:85 errores:0 perdidos:0 overruns:0 carrier:0
          colisiones:0 long.colaTX:1000
          Bytes RX:7872 (7.8 KB)  TX bytes:7747 (7.7 KB)

lo        Link encap:Bucle local  
          Direc. inet:127.0.0.1  Másc:255.0.0.0
          Dirección inet6: ::1/128 Alcance:Anfitrión
          ACTIVO BUCLE FUNCIONANDO  MTU:65536  Métrica:1
          Paquetes RX:55 errores:0 perdidos:0 overruns:0 frame:0
          Paquetes TX:55 errores:0 perdidos:0 overruns:0 carrier:0
          colisiones:0 long.colaTX:1
          Bytes RX:4323 (4.3 KB)  TX bytes:4323 (4.3 KB)

roberto@serverob2:~$ cat /etc/resolv.conf
# Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
#     DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 172.18.22.1
nameserver 172.18.22.2
search skynet.edu
roberto@serverob2:~$ cat /etc/network/interfaces
# interfaces(5) file used by ifup(8) and ifdown(8)
auto lo
iface lo inet loopback

#Tarjeta de red enp0s3

auto enp0s3
iface enp0s3 inet static


	address 172.18.22.2
	gateway 172.18.0.1
	netmask	255.255.0.0
	dns-domain skynet.edu
	dns-nameservers 172.18.22.1
	dns-nameservers 172.18.22.2
roberto@serverob2:~$

```

### Configurar el fichero `/etc/bind/named.conf.local`<a name="12"></a>

```console

roberto@serverob2:~$ sudo nano /etc/bind/named.conf.local
[sudo] password for roberto:
roberto@serverob2:~$ sudo cat /etc/bind/named.conf.local
#
# Do any local configuration here


# Consider adding the 1918 zones here, if they are not used in your
# organization
#include "/etc/bind/zones.rfc1918";


# Añadir en /etc/bind/named.conf.local
# Archivo para búsquedas directas

zone "skynet.edu" {
	type slave;
	file "/var/cache/bind/db.skynet.edu";
	masters {172.18.22.1;};
};

# Archivo para búsquedas inversas

zone "18.172.in-addr.arpa" {
	type slave;
	file "/var/cache/bind/db.172";
	masters {172.18.22.1;};
};
roberto@serverob2:~$

```

Si nos fijamos en le fichero de configuración solo cambiamos el type a slave y decimos donde queremos que se guarden los registros de zona directa y zona inversa y cual es el master con su dirección IP.


Para realizar las comprobaciones de que funciona correctamente el servidor DNS2 solo tenemos que parar el servicio en el servicio DNS1.

```console
roberto@serverob:~$ /etc/init.d/bind9 stop
[ ok ] Stopping bind9 (via systemctl): bind9.service.
roberto@serverob:~$ /etc/init.d/bind9 status
● bind9.service - BIND Domain Name Server
   Loaded: loaded (/lib/systemd/system/bind9.service; enabled; vendor preset: en
  Drop-In: /run/systemd/generator/bind9.service.d
           └─50-insserv.conf-$named.conf
   Active: inactive (dead) since sáb 2017-10-28 02:24:14 WEST; 6min ago
     Docs: man:named(8)
  Process: 3209 ExecStop=/usr/sbin/rndc stop (code=exited, status=0/SUCCESS)
  Process: 3159 ExecStart=/usr/sbin/named -f -u bind (code=exited, status=0/SUCC
 Main PID: 3159 (code=exited, status=0/SUCCESS)

oct 28 02:24:14 serverob named[3159]: received control channel command 'stop'
oct 28 02:24:14 serverob named[3159]: shutting down: flushing changes
oct 28 02:24:14 serverob named[3159]: stopping command channel on 127.0.0.1#953
oct 28 02:24:14 serverob named[3159]: stopping command channel on ::1#953
oct 28 02:24:14 serverob named[3159]: no longer listening on ::#53
oct 28 02:24:14 serverob named[3159]: no longer listening on 127.0.0.1#53
oct 28 02:24:14 serverob named[3159]: no longer listening on 172.18.22.1#53
oct 28 02:24:14 serverob named[3159]: exiting
oct 28 02:24:14 serverob systemd[1]: Stopped BIND Domain Name Server.
oct 28 02:30:06 serverob systemd[1]: Stopped BIND Domain Name Server.
roberto@serverob:~$


```

Solo tenemos que volver a ejecutar el comando `nslookup` para ver que servidor me esta resolviendo.

```console

roberto@serverob:~$ nslookup server
Server:		172.18.22.2
Address:	172.18.22.2#53

server.skynet.edu	canonical name = serverob.skynet.edu.
Name:	serverob.skynet.edu
Address: 172.18.22.1

roberto@serverob:~$ nslookup www.google.es
Server:		172.18.22.2
Address:	172.18.22.2#53

Non-authoritative answer:
Name:	www.google.es
Address: 216.58.210.227

roberto@serverob:~$ nslookup printer
Server:		172.18.22.2
Address:	172.18.22.2#53

Name:	printer.skynet.edu
Address: 172.18.22.4


```

Es importante que en el equipo cliente y en los servidores tengan en el `resolv.conf` la siguientes dirección de DNS.

```console
roberto@serverob2:~$ cat /etc/resolv.conf
# Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
#     DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 172.18.22.1
nameserver 172.18.22.2
search skynet.edu

```

### Comprobación de resolución de Nombre en el Equipo Cliente.<a name="13"></a>


Necesitamos antes configurar los siguientes ficheros

```console
roberto@clienterob:~$ sudo cat /etc/resolv.conf
[sudo] password for roberto:
# Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
#     DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 172.18.22.1
nameserver 172.18.22.2
roberto@clienterob:~$ sudo cat /etc/network/interfaces
# interfaces(5) file used by ifup(8) and ifdown(8)
auto lo
iface lo inet loopback

# Tarjeta de red 1

auto enp0s3
iface enp0s3 inet static

	address 172.18.22.3
	netmask 255.255.0.0
	gateway 172.18.0.1
	dns-nameservers 172.18.22.1
	dns-nameservers 172.18.22.2
roberto@clienterob:~$


```
Si tenemos en el resolv.conf la IP

```console

roberto@clienterob:~$ nslookup www.google.es
Server:		172.18.22.2
Address:	172.18.22.2#53

Non-authoritative answer:
Name:	www.google.es
Address: 216.58.210.131

roberto@clienterob:~$ nslookup server.skynet.edu
Server:		172.18.22.2
Address:	172.18.22.2#53

server.skynet.edu	canonical name = serverob.skynet.edu.
Name:	serverob.skynet.edu
Address: 172.18.22.1

roberto@clienterob:~$ nslookup printer.skynet.edu
Server:		172.18.22.2
Address:	172.18.22.2#53

Name:	printer.skynet.edu
Address: 172.18.22.4

roberto@clienterob:~$ nslookup clienterob.skynet.edu
Server:		172.18.22.2
Address:	172.18.22.2#53

Name:	clienterob.skynet.edu
Address: 172.18.22.3

```
