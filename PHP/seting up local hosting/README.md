La siguiente nota está basada en [esta](http://www.linuxandubuntu.com/home/how-to-setup-a-web-server-and-host-website-on-your-own-linux-computer) liga

# Creando un servidor local para poder usar un `localhost`al momento de diseñar/programar una página web:

Para este propósito utilizaremos:
* Apache
* MySQL
* PHP
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
```

