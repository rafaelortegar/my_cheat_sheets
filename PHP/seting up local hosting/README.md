La siguiente nota está basada en [esta](http://www.linuxandubuntu.com/home/how-to-setup-a-web-server-and-host-website-on-your-own-linux-computer) liga, asi como estas: [liga 1](https://www.howtoforge.com/ubuntu-lamp-server-with-apache2-php5-mysql-on-14.04-lts), [liga 2](https://vitux.com/how-to-install-php5-and-php7-on-ubuntu-18-04-lts/). 

# Creando un servidor local para poder usar un `localhost`al momento de diseñar/programar una página web:

Para este propósito utilizaremos:
* [Apache](https://github.com/rafaelortegar/my_cheat_sheets/blob/master/PHP/seting%20up%20local%20hosting/README.md#instalaci%C3%B3n-de-apache)
* [MySQL](https://github.com/rafaelortegar/my_cheat_sheets/blob/master/PHP/seting%20up%20local%20hosting/README.md#instalaci%C3%B3n-de-mysql)
* [PHP](https://github.com/rafaelortegar/my_cheat_sheets/blob/master/PHP/seting%20up%20local%20hosting/README.md#instalaci%C3%B3n-de-php)
* HTML se usa para programar la interfaz con el usuario, pero el código de HTML se pondrá en su [carpeta correspondiente](https://github.com/rafaelortegar/my_cheat_sheets/tree/master/HTML).

## Instalación de Apache:
`sudo apt-get updatesudo apt-get install apache2`

Para revisar si la instalación fue correcta:
`sudo service apache2 restart`
este comando es para reinciar el web server.

Despues de estos dos comandos, solo bastará con abrir el explorador e ingresar a la dirección "localhost" sin poner el número de puerto, aunque de ser necesario ponerlo, será el puerto 80.

Para cambiar la dirección del puerto, se tiene que editar el archivo de configuración en `/etc/apache2/ports.conf`  y cambiar el puerto 80 por el puerto que deseas.

## Instalación de MySQL

`sudo apt-get install mysql-server mysql-client`

 &rarr; Aparición del error: `ERROR 1698 (28000): Access denied for user 'root'@'localhost'`
Para solucionarlo:
``` SQL
$ sudo mysql -u root # I had to use "sudo" since is new installation

mysql> USE mysql;
mysql> SELECT User, Host, plugin FROM mysql.user;

+------------------+-----------------------+
| User             | plugin                |
+------------------+-----------------------+
| root             | auth_socket           |
| mysql.sys        | mysql_native_password |
| debian-sys-maint | mysql_native_password |
+------------------+-----------------------+

mysql> USE mysql;
mysql> CREATE USER 'TU_USUARIO_DE_SISTEMA'@'localhost' IDENTIFIED BY '';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'TU_USUARIO_DE_SISTEMA'@'localhost';
mysql> UPDATE user SET plugin='auth_socket' WHERE User='TU_USUARIO_DE_SISTEMA';
mysql> FLUSH PRIVILEGES;
mysql> exit;
```
o bien, en algunos sistemas (e.g., Debian stretch), el plugin 'auth_socket' es llamado 'unix_socket', entonces, el comando de SQL debería ser:

```SQL
$ sudo mysql -u TU_USUARIO_DE_SISTEMA 

mysql> USE mysql;
mysql> CREATE USER 'TU_USUARIO_DE_SISTEMA'@'localhost' IDENTIFIED BY 'TU_CONTRASEÑA DE USUARIO'; # Si no quieres asignar una contraseña, dejarlo como ''
mysql> GRANT ALL PRIVILEGES ON *.* TO 'TU_USUARIO_DE_SISTEMA'@'localhost';
mysql> UPDATE user SET plugin='unix_socket' WHERE User='TU_USUARIO_DE_SISTEMA';
mysql> FLUSH PRIVILEGES;
mysql> exit;

$ service mysql restart
```

Para acceder a la base de datos:

```SQL
mysql -u TU_USUARIO_DE_SISTEMA -p
```
con la nueva versión de MySQL, el comando es el siguiente:

```bash
$  sudo mysql -u root -p
``
```SQL
 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'TU_CONTRASEÑA DE USUARIO';
```
después, para iniciar y parar el SQL server:
```bash
$  sudo service mysql stop
$  sudo service mysql start
```

## Instalación de PHP
Primero, agregamos el repositorio `ondrej/php`, que contiene las versiones actualizadas de PHP y hacemos un update.
```bash
$ sudo add-apt-repository ppa:ondrej/php
$ sudo apt-get update
```
Después, instalamos PHP con el siguiente comando:
```bash
$ sudo apt-get install -y php<version> #por ejemplo: sudo apt-get install -y php7.2
```

Para revisar la instalación, podemos revisar la versión:
```bash
$ php -v
```



