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


## 4. Instalación del cliente

En nuestro caso primero probamos con el cliente `ekiga`, pero tuvimos bastantes problemas para realizar la conexión, el servidor los detectaba pero no realizaba llamadas, por lo que intentamos utilizar el cliente `3cx softphone`. Para ello vamos a descargar el programa desde su página oficial.

![](img/051.png)

- Al instalarlo nos solicita un perfil SIP, por lo que añadiremos el perfil de `kevin`.

  ![](img/052.png)

  ![](img/053.png)

  ![](img/054.png)

Una vez especificada la extensión y las credenciales necesarias vemos que el teléfono esta operativo.

![](img/055.png)

- Instalamos el softphone y repetimos todos los pasos en un nuevo equipo cliente, pero esta vez con la configuración SIP de `roberto`.

![](img/056.png)

## 4.1. Comprobaciones

Vamos a realizar llamadas de comprobación:

- Preparamos los telefonos y vemos que ambos estan a la espera.

  ![](img/057.png)

- Realizamos una llamada desde `Kevin` hasta `Roberto`, y vemos que efectivamente `Roberto` recibe la llamada.

![](img/058.png)

- Esto también vemos que funciona de viceversa.

![](img/059.png)

- Si respondemos a la llamada podemos comprobar que se inicia la conversación y sale un temporizador de tiempo de llamada

![](img/060.png)

- Para finalizar si accedemos a la interfaz web de `Elastix` podemos comprobar que ambos usuarios están conectados.

![](img/061.png)

- En el apartado de `teléfonos` podemos comprobar que los teléfonos conectados se encuentran a través de clientes Windows y que están siendo usando con las cuentas de `kevin` y `roberto`

![](img/062.png)

## ANEXO. Clientes móviles

En este apartado no pudimos completarlo por que no tuvimos forma de establecer conexión con la red de clase, pero si pudimos hacer la instalación del cliente.

- Para esto solo descargarmos la aplicación de la PlayStore en android.

  ![](img/065.jpg)

- La interfaz de la aplicación es similar a la versión de escritorio.

  ![](img/063.jpg)

- Y como indicamos previamente no pudimos establecer la conexión porque no teníamos acceso a la red y nuestro servidor no dispone de una IP Externa valida. 

Una vez dicho esto podemos dar por finalizada la práctica.
