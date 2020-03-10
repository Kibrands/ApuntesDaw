# Unidad 1: Arquitecturas web

## Índice
--- 
- ### Introducción
- ### El protocolo HTTP
- ### Arquitecturas web
- ### Plataformas web
- ### Despliegue en Internet

## Introducción


### En esta Unidad aprenderemos a

- Valorar los fundamentos y protocolos en los que se basa el funcionamiento de un servidor Web.
- Clasificar y describir los principales servidores de aplicaciones.
- Instalar y configurar de forma básica servidores Web.
- Realizar pruebas de funcionamiento de los servidores web.


### ¿Qué es Internet?

![Internet](assets/internet.png)


### ¿Qué es Internet?

- Un conjunto de **nodos** (equipos) conectados en forma de malla parcial.
- Un conjunto de **protocolos** para comunicar dichos nodos.
- Cada protocolo permite ofrecer un **servicio** o parte de él.
- Diseño inicial **cliente/servidor**. 


### Protocolos de Internet

- **HTTP** (World Wide Web)
- **FTP** (Transferencia de archivos)
- **DNS** (Resolución de nombres)
- **SMTP**, **POP**, **IMAP** (Correo eléctrónico)
- **RIP**, **OSPF**, **BGP** (Enrutamiento de paquetes)
- **Telnet**, **SSH** (Conexión remota por terminal)
- **VNC**, **RDP** (Conexión remota gráfica)
- ... muchos más


###  Localizador Uniforme de Recursos (URL)

- Identifica un recurso en Internet. La forma básica es:
  ```
  protocolo://servidor:puerto/ruta/recurso
  ```
- En algunos casos puede incluir parámetros, credenciales, etc. Ejemplos:
  ```
  http://192.168.1.1/directorio/archivo.html
  ftp://archivos.example.com/descargas/ubuntu.iso
  https://pepe:1234@musica.com:1443/rock/descargar.php?album=37&formato=mp3
  ```



## El protocolo HTTP


### Características

- Permite el **servicio WWW**.
- Desarrollado por el World Wide Web Consortium y la Internet Engineering Task Force.
- El servidor atiende peticiones en el **puerto 80**.
- La versión más usada actualmente es HTTP/1.1 ( RFC 2616 ).
- También existe la versión HTTP/2, todavía poco usada.
- Existe la versión segura, que es HTTPS, en la que el servidor atiende en el **puerto 443**.  
- Es es protocolo sin estado: no guarda ninguna información sobre conexiones anteriores.


### Transacción HTTP

![Transacción HTTP](assets/transaccion-http.png)


### Ejemplo de petición

```
GET /index.html HTTP/1.1
Host: www.example.com
```


### Ejemplo de respuesta

```
HTTP/1.1 200 OK
Date: Mon, 23 May 2005 22:38:34 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 138
Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux)
Connection: close

<html>
<head>
  <title>An Example Page</title>
</head>
<body>
  Hello World, this is a very simple HTML document.
</body>
</html>
``` 


### Métodos HTTP
#### Métodos básicos

- **GET**
- **POST**
- **PUT**
- **DELETE**


### Métodos HTTP
#### Otros métodos

- **HEAD**
- **OPTIONS**
- **CONNECT**
- **PATCH**
- **TRACE**

https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_hipertexto


### Códigos de respuesta HTTP

- **1xx**: Mensajes.
- **2xx**: Operación exitosa.
- **3xx**: Redirección. 
- **4xx**: Errores del cliente.
- **5xx**: Errores del servidor.

[Lista de códigos de estado (en inglés)](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)


### Cabeceras de la petición

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Accept	        | Accept: text/html	            | Tipos de contenido que se admiten como respuesta.
Accept-Charset	| Accept-Charset: utf-8	        | Juegos de caracteres admitidos.
Accept-Encoding	| Accept-Encoding: gzip, deflate| Lista de codificaciones (compresión) admitidas.


### Cabeceras de la petición

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Accept-Language	| Accept-Language: en-US	    | Lista de idiomas admitidos como respuesta.
Host            | Host: en.wikipedia.org:8080   | Nombre de dominio del servidor (:puerto si es distinto de 80)
User-Agent      |User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:12.0) | Agente del usuario.
...             | ...                           | ...


### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Content-Encoding| Content-Encoding: gzip        | Codificiación de los datos enviados.
Content-Language| Content-Language: es          | Idioma en el que está el contenido.
Content-Type    | Content-Type: text/html; charset=utf-8 | Tipo MIME del contenido.


### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Server          | Server: Apache/2.4.1 (Unix)   | Servidor web.
Status          | Status: 200 OK                | Código de estado.
...             | ...                           | ...


### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
text/plain            | Texto plano
text/html             | Texto en formato HTML
text/css              | Hoja de estilo en cascada
application/javascript| Código javascript
application/json      | Datos en formato JSON
image/jpeg            | Imagen en formato JPEG
image/png             | Imagen en formato PNG


### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
image/svg+xml         | Imagen vectorial SVG
audio/ac3             | Audio en formato AC3
audio/ogg             | Audio en formato OGG Vorbis
video/H264            | Video con codificación H.264
...                   | ...


### Petición HTTP

![Petición HTTP](assets/peticion-http.png)



## Arquitecturas web


### Capas de la arquitectura

- **Capa de presentación**: se encarga de la navegabilidad, validación de los datos de entrada, formateo de los datos de salida, presentación de la web, etc.; se trata de la capa que se presenta al usuario.
- **Capa de negocio**: recibe las peticiones del usuario y desde donde se le envían las respuestas; en esta capa se verifican que las reglas establecidas se cumplen.
- **Capa de acceso a datos**: es la formada por determinados gestores de datos que se encargan de almacenar, estructurar y recuperar los datos solicitados por la capa de negocio.


### Modelo de 2 capas

![Web 2 capas](assets/web-2-capas.png)


### Modelo de 3 capas

![Web 3 capas](assets/web-3-capas.png)


### Páginas estáticas

- **HTML**
- **CSS**
- **Javascript**
- **Assets** (imágenes, fuentes de letra, ...)


### Páginas dinámicas

- **PHP**: PHP Hypertext Preprocessor.
- **JSP**: JavaServer Pages. 
- **ASP**: Active Server Pages. 


## Plataformas

- **LAMP**. Linux + Apache + MySQL + PHP. **Libre**.
- **WISA**. Windows + IIS + SQLServer + ASP. **Propietaria**.


### Servidores web

- **Apache**
- **nginx**
- **IIS** (Internet Information Services de Microsoft)
- **Tomcat** (servidor orientado a desarrollo Java)


### Apache
#### Directorios y archivos de configuración

![Apache2](assets/apache2-files.png)



## Despliegue en Internet


### Escalabilidad

- **Vertical** -> Servidores más potentes.  
- **Horizontal** -> Más servidores.


### Tipos de servidores
#### Evolución

- Sin virtualización (hosting tradicional)
  - **Servidor dedicado**
  - **Servidor compartido**

- Con virtualización 
  - Servidor virtual (**VPS** - Virtual Private Server)
  - Nube (**Cloud**)


### La nube
#### Tipos de servicios ###

- **IaaS**. Infraestructura como Servicio. 
- **PaaS**. Plataforma como Servicio.
- **SaaS**. Servicio como Servicio. 

[Diferencias entre IaaS, PaaS y SaaS](https://www.genbeta.com/desarrollo/entendiendo-la-nube-el-significado-de-saas-paas-y-iaas)


### La nube
#### Proveedores ###

![Amazon - GCP - Azure](assets/cloud-amazon.png)


### La nube
#### Proveedores ###

![Heroku - Openshift - DigitalOcean](assets/cloud-heroku.png)
