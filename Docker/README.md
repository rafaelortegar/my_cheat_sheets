# Instalación:
La guía oficial de docker para la instalación se encuentra en la siguiente [liga](https://docs.docker.com/engine/install/ubuntu/), pero básicamente se deben seguir los siguientes pasos:

**Desinstalar versiones anteriores**

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

**Instalación**
Seguimos con el método de [instalación utilizando el repositorio](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository):

1. Actualizar paqueterías e instalar lo necesario para permitir a `apt` que use un repositorio vía HTTPS:

```bash


 sudo apt-get update
 sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

2. Añadir la llave GPG oficial de Docker:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

3. añadir el repositorio en su versión "stable"

```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

4. Instalar Docker engine en su versión _latest_

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
O en una versión específica:

se revisan las versiones disponibles:
```bash
apt-cache madison docker-ce
```
Se instala la versión deseada  
```bash
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

5. Crear el grupo `docker`

```bash
sudo groupadd docker
```

6. Agregar tu usuario al grupo de `docker`

```bash
sudo usermod -aG docker $USER
```
7. Activar los cambios en los grupos

```bash
newgrp docker
```
8. Reiniciar el daemon de docker

```bash
sudo service docker restart
```

9. Verificar que puedes correr comandos de docker sin utilizar sudo

```bash
docker run hello-world
```

**Nota:** Si corriste algunos comandos utilizando `sudo` antes de añadir el usuario al grupo de `docker`, es posible que el directorio `~/.docker/` contenga un error, creándose con permisos incorrectos.

Para resolver este problema, se necesita remover este directorio, o cambiar al propietario y los permisos con los siguientes comandos:

```bash
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```

## Remover imagenes de docker
con esta [liga](https://www.freecodecamp.org/news/how-to-remove-images-in-docker/)

## Taggeo automático de imágenes de docker
Con esta [liga](https://blog.container-solutions.com/tagging-docker-images-the-right-way)

## [Dockerfiles de imagenes propias](https://github.com/rafaelortegar/my_Dockerfiles):


## Ligas a revisar
* [liga](https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook)
* [liga](https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html)
* [liga](https://github.com/jupyter/docker-stacks)
* [liga](https://github.com/jupyter/docker-stacks/blob/master/datascience-notebook/Dockerfile)
* [liga](https://hub.docker.com/r/jupyter/base-notebook/dockerfile)
