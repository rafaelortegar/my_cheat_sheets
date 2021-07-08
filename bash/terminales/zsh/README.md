# Instalación

Correr el siguiente comando para instalar zsh

```bash
sudo apt update
sudo apt upgrade
sudo apt install zsh
```

## Hacer ZSH como el shell por default
```bash
# (optional) set default shell
chsh -s $(which zsh)

# Verify, open new terminal
echo $SHELL
```

Para aplicar los cambios, solo sería necesario cerrar la terminal y abrir una nueva.

## Si lo necesitas, puedes volver a hacer bash como default Shell
```bash
chsh -s $(which bash)
```

## Instalación de oh-my-zsh
Por lo general, se puede requerir instalar [oh-my-zsh](https://ohmyz.sh/), lo cual se puede realizar con el siguiente comando:
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
