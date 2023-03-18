# apache-php
## Instalación de Apache+Virtual Host
#### Daniel Otero Ferreira 2º ASIR

Creare una carpeta _‘apachehost’_ donde trabajar.

Luego abriré una terminal y ejecutaré el comando _‘docker pull php:apache’_ para descargar una imagen con php y apache.

A continuación crearé un archivo _docker-compose.yml_ e introduciré lo siguiente:

‘version: "3.8"


services:
asir_apache:
image: php:apache
container_name: asir_apache
ports:
- "80:80"
volumes:
- ./html:/var/www/html’


En el fichero establezco un servicio llamado _‘asir_apache’_ que usará la imagen _‘php:apache’_ que he descargado antes y vinculo la carpeta que crearé _‘html’_ con la arpeta _‘/var/www/html’_ del contenedor.

Después de crear la carpeta _‘html’_ crearé un fichero llamado _‘html.index’_ dentro y añadiré lo siguiente:

‘<!DOCTYPE html>
<html>
<head>
<title>Hola mundo</title>
</head>
<body>
<h1>Hola mundo</h1>
<?php echo "La versión de PHP es " . phpversion(); ?>
</body>
</html>’

Introduzco php para comprobar que php funcione.

Utilizo el comando _‘docker-compose up -d’_ para iniciar el servicio:

Intoduzco _‘http://localhost/’_ en el navegador y debería aparecer un ‘Hola Mundo’.

Para comprobar que php funciona, crearé un archivo _‘info.php’_ en _‘html’_ y le añadire _‘<?php phpinfo(); ?>’_ y abrire  _‘http://localhost/info.php’_ en el navegador.

Me aparecerá una pestaña indicando información sobre mi versión php.
