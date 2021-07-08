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

## Si lo necesitas, puedes volver a hacer bash como default Shell
```bash
chsh -s $(which bash)
```

