
# Práctica IIS-Parte 4 Certificado SSL


## 1. Crea una nueva zona de búsqueda directa en los servicios DNS asociado al dominio miEmpresa.

Lo primero que tenemos que crear es una zona directa nueva en el DNS llamada `miempresa.edu`.

![](img/001.png)

Tenemos que crear dos registros en el DNS tipo `A=serverob2` y `CNAME=www`.

![](img/002.png)


### 1.1 Creación de Directorio E:\miempresa

Vamos al disco duro E:\ y creamos el directorio `miempresa`

![](img/005.png)

## 2. Creación de Sitio Web en IIS

Entramos en el administrador de IIS y agregamos un `sitio web nuevo`.

![](img/003.png)

Se comprueba que hemos creado el sitio web nuevo.

![](img/004.png)

Ya tenemos el sitio web `www.miempresa.edu` operativa, agregamos un index.html para comprobar que funciona con el puerto 80

![](img/006.png)

### 2.1 Creación de un subdominio llamado `pagos.miempresa.edu`, pero debemos configurarlo mediante conexión segura vía `https`.

- Primero tenemos que ir a los DNS para agregar un subdominio llamado `pagos`.

![](img/007.png)

![](img/008.png)

- Agregamos un sitio Web nuevo llamado `pagos.miempresa.edu`

![](img/008.png)

Por ahora lo agregamos sin `https`, necesitamos generar un certificado autofirmado. Ese será nuestro siguiente paso.

![](img/009.png)

### 2.2 Generar un certificado autofirmado desde IIS.

- Vamos al administrador de IIS y nos situamos en la página principal de serverob2 y hacemos clic en el `certificados de servidor`

![](img/010.png)

- Luego vamos al cuadro de la derecha y le damos `crear certificado autofirmado`

![](img/011.png)

- Se nos abre una ventana nueva, para escribir nombre del certificado.

![](img/012.png)

- Ya tenemos creado el certificado

![](img/013.png)

- Volvemos al sitio Web que creamos de `pagos.miempresa.edu` y con el botón secundario le damos `agregar modificaciones`.

![](img/014.png)

- le damos agregar enlace de sitio y ente caso el tipo `https` y buscamos el certificado SSL.

![](img/015.png)

- Luego solo tenemos que eliminar la de `http`.

![](img/016.png)

- Comprobamos que funciona correctamente la página `https://pagos.miempresa.edu`

![](img/017.png)

![](img/018.png)

## 3 Creación de Sitio Web para `https://tienda.miempresa.edu`

Tenemos que ir al administrador de IIS y creamos el sitio Web nuevo.

![](img/019.png)

### 3.1 Agregar subdominio nuevo en el DNS.

Solo tenemos que ir a los DNS y agregar el dominio de tienda.

![](img/020.png)

![](img/021.png)

### 3.2 Comprobamos que funciona correctamente desde el cliente.

![](img/022.png)

### 3.3 Creación de Sitio Seguro `htpps://tienda.miempresa.edu` con la generación de un certificado Digital a través de la aplicación OpenSSL.

![](img/023.png)

- Escribimos el nombre de la solicitud de certificado.

![](img/024.png)

- Le damos siguiente y en este caso tiene que ser RSA la critográficos y longitud en bits 2048.

![](img/025.png)

- La ruta donde vamos a guardar los datos que vamos a dar a una entidad certificadora.

![](img/026.png)

- Comprobamos como genera el fichero.

![](img/027.png)

#### 3.3.1 Instalación de OpenSSL para simular que es una empresa certificadora.

- Descargamos el programa OpenSSL y los instalamos, el proceso de instalación es muy sencillo, solo debemos seguir el asistente de Windows.

![](img/028.png)

- Termina la instalación de OpenSSL

![](img/029.png)

- Comenzamos con la generación del certificado mediante OpenSSL, primero generamos la clave privada de la entidad certificadora.

![](img/030.png)

- Comprobación del fichero generado.

![](img/031.png)

- Generamos el certificado digital de la entidad certificadora.

![](img/032.png)

- Comprobación del fichero generado.

![](img/033.png)

- Certificado digital de nuestra Web `https://tienda.miempresa.edu`

![](img/034.png)

- Comprobación del fichero generado.

![](img/035.png)

- Ya el certificado digital para nuestra WEB.

- Volvemos al IIS y vamos a nuestro serverob2 y completamos la solicitud de certificado.

![](img/040.png)

- Buscamos la ruta donde se genero el fichero de la certificado digital llamado `iis.crt`

![](img/036.png)

- Le damos acepta y ya tenemos nuestro certificado digital.

- Volvemos a nuestro sitio Web tienda.miempresa.edu y tenemos que borrar el enlace de sitio de web `http` por `https`.

![](img/037.png)

- Desde el cliente comprobamos que podemos acceder a la página Web.
- Este mensaje nos sale porque no tenemos una empresa certificado que lo confirme por lo tanto no es un certificado confiable para trabajar por Internet.

![](img/038.png)

![](img/039.png)
