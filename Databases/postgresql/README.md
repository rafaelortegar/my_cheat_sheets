Esta nota está basada en la siguiente [liga](https://www.youtube.com/watch?v=VNy2nhho9Pg) y esta [otra](https://www.youtube.com/watch?v=-LwI4HMR_Eg)

## Instalación
```sql
sudo apt-get update
sudo apt-get install postgresql postgresql.contrib
```

## holis
```sql
sudo -i -u postgres
```

### Accediendo al postgres prompt
```sql
psql
```

## Otra forma
```sql
sudo -u postgres psql
```

## crear un nuevo rol/usuario
```sql
sudo -u postgres createuser --interactive
```
* ingresas el nombre
* dices si es superuser o no

## create a database
```sql
sudo -u postgres createdb nombredebasededatos
```

### revisar la conexión
```sql
sudo -u postgres psql

## postgres=# \conninfo
```

### conectarse 
```sql
sudo -u nombredebasededatos psql
```

## ubicacion del configuration file
```sql
ls /etc/postgresql/<version de postgres instalada>/main
```
## revisar el estatus
```sql
#service postgresql
service postgresql status
```

postgres es el default user para postgres

### Para cambiar al usuario postgres
```sql
sudo su postgres
```

## Dentro de postgres

lista de bases de datos
```sql
\l
```

### cambiar contraseña del user postgres
```sql
postgres=# ALTER USER postgres WITH PASSWORD 'test123';
```
no es buena práctica usar el root user de postgres, entonces creamos un nuevo usuario

### crear nuevo usuario:
```sql
postgres=# CREATE USER user_1 WITH PASSSWORD 'test123';
```

### Listar los roles que existen de postgres:
```sql
\du
```

### convertir a un usuario existente en superuser
```sql
postgres=# ALTER USER user_1 WITH SUPERUSER          
```

### eliminar a un user:
```sql
postgres=# DROP USER user_2
```
## manual de psql
```sql
man psql
#sales con q
```
en el video recomiendan pgAdminIII (aplicación de desktop)

```sql

```


```sql

```

```sql

```


```sql

```


```sql

```


```sql

```


```sql

```


```sql

```
