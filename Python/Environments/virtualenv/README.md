Esta nota está basada en el video de la siguiente [Liga](https://youtu.be/N5vscPTWKOk)

## Instalación
Dentro de python, escribir la siguiente línea:

```bash
pip install virtualenv
```

virtualenv sirve para separar los diferentes ambientes de desarrollo de cada proyecto.

## Crear un nuevo ambiente virtual
```bash
virtualenv nombre_de_proyecto
```

## Entrar a un ambiente virtual
```bash
source nombre_de_proyecto/bin/activate
```

## Saber el ambiente en que nos encontramos:
```bash
which python
```
o

```bash
which pip
```

## Instalando paquetes:
```bash
pip install nombre_de_paquete
```

## Listar los paquetes instalados en el ambiente virtual
```bash
pip list
```

## Exportar los paquetes a un Requirements.txt
```python
pip freeze --local > requirements.txt  
#la bandera --local sirve para que se introduzcan solamente los paquetes en el ambiente virtual, si quiero incluir todos los paquetes en el python global, uso --global
```

## Entrar al requirements.txt
```bash
cat requirements.txt
```

## Salir del ambiente virutal
```bash
deactivate
```


## ver los ambientes en la carpeta:
Solamente escribimos en bash:
```bash
ls
```

## borrar un ambiente virtual:
Primero desactivas el ambiente virutal y después, en bash:
```bash
rm -rf nombre_de_proyecto
```

## Crear un ambiente virtual con un archivo requirements:
```bash
virtualenv -p /usr/bin/python2.6 nombre_del_nuevo_proyecto
```
para activar el nuevo ambiente:
```bash
source nombre_del_nuevo_proyecto/bin/activate
```
