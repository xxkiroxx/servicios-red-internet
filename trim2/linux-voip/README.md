# U9-A1 | Instalación y Configuración del Servicio VoIP en Linux


Vamos a realizar la práctica de `VOIP` en Linux con la distribución de `Elastix`. Tenemos que descargar en la página oficial de `Elastix` https://www.elastix.org/es/.

![](img/001.png)

Le damos a descargar `Elastix ver 5.0`.

![](img/002.png)

Le damos a Download y tenemos descargado la iso de `Elastix`.

## 1. Preparando la máquina virtual para Elastix.

Abrimos el virtual box y creamos una máquina nueva.

![](img/003.png)

Seleccionamos la iso de elastix y la colocamos en el `CD-ROM` virtual.

![](img/004.png)

## 2. Instalación de Elastix.

Comenzamos la Instalación en el modo gráfico.

![](img/005.png)

Escribimos el nombre del host en nuestro caso `kevinrobert`.

![](img/006.png)

Seleccionamos el idioma = `Español`

![](img/007.png)

Seleccionamos la ubicación = `Español`

![](img/008.png)

Escribimos la contraseña del usuario `root`.

![](img/009.png)

Seleccionamos nuestro horario en `Islas Canarias`.

![](img/010.png)

Comenzamos con la Instalación por lo tanto no pedirá una confirmación de que las particiones se van a eliminar.

![](img/011.png)

Ya tenemos instalado el `elastix`.

Tenemos que seleccionar la opción 1 para poder configurar `elastix` mediante el navegador.

![](img/012.png)

Comprobamos que nos indica nuestra ip privada `172.18.19.29` y el puerto `5015`.

![](img/013.png)

## 3. Configuración de VOIP

Abrimos un navegador en un equipo cliente y establecemos la siguiente IP.

- Nos pedirá que tenemos que registrarnos en la siguiente página y nos dará una clave para acceder a la Configuración del software.


![](img/014.png)

Tenemos que registranos en el formulario y por correo obtendremos el código.

![](img/015.png)

En el correo nos sale una verificación y solo debemos darle al enlace.

![](img/016.png)

Ya tenemos el código y lo copiamos en el navegador.

![](img/017.png)

Con el código le damos siguiente.

![](img/018.png)

Establecemos el usuario y su contraseña.

![](img/019.png)

En este caso no vamos a utilizar la IP pública, una privada.

![](img/020.png)

El tipo de IP pública es estática. Pero como habíamos comentado en el apartado anterior será una IP privada.

![](img/021.png)

Escribimos nuestro subdominio.

![](img/022.png)

En la siguiente captura son los puertos que vamos a utilizar para los siguiente protocolos.

![](img/023.png)

Seleccionamos el adaptador de red.

![](img/024.png)

Ya comienza la Configuración y solo debemos esperar.

![](img/025.png)

En la siguiente captura es la longitud que nosotros queremos para la extensión de llamadas.

![](img/026.png)

Escribimos el email para el usuario `Admin`.

![](img/027.png)

Seleccionamos el idioma

![](img/028.png)

Escribimos el primer operador con su número de extensión.

![](img/029.png)

Seleccionamos nuestra ubicación.

![](img/030.png)

Seleccionamos en que idioma queremos nuestro prompts = `Español`

![](img/031.png)

La siguiente captura es la confirmación del registro.

![](img/032.png)

Esperamos que termine de configurar con los parámetros configurados.

![](img/033.png)

Ya tenemos configurado  nuestro servicio de `VOPIP`.

![](img/034.png)

Comprobamos que podemos entrar y administrar el software de `VOIP`.

![](img/035.png)

Vemos todas las acciones que nos deja administrar.

![](img/036.png)

Agregamos una nueva extensión.

![](img/037.png)

![](img/038.png)

Comprobamos que ya tenemos registrada 3 extensión.

![](img/039.png)

## 4. Equipo Cliente Instalación de ekiga

Abrimos una terminal y instalamos el software `ekiga`.

![](img/040.png)

Abrimos el programa y le damos cuentas y luego añadir una cuenta SIP.

![](img/041.png)

![](img/043.png)

Escribimos los siguiente parámetros para que se pueda conectar a nuestro sistema de `VOIP`.

![](img/044.png)

![](img/045.png)

Realizamos los mismo pasos con otro cliente, en el que incluiremos al usuario `kevin`.

![](img/048.png)

En la siguiente captura vemos como ambos están funcionando al mismo tiempo.

![](img/046.png)

- Si accedemos a la interfaz web de elastix podemos ver que ambas cuentas están configurados al mismo tiempo en este momento.

  ![](img/047.png)

- Y en el apartado de los teléfonos podemos comprobar que ambas sesiones están en los softphone de `Ekiga`.

  ![](img/049.png)

## 5. Comprobar con una llamada
