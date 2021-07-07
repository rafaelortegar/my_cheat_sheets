Una buena guía de configuración de PyEnv está en esta [Liga](https://www.youtube.com/watch?v=fv8YxO3AJqg&t=701s)
[revisar](https://www.youtube.com/watch?v=3J02sec99RM)


# Instalación:
**Instalar paqueterías requeridas:** Mencionadas [aqui](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)
```bash
sudo apt-get update; sudo apt-get install make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

**Instalación con curl desde github**

```bash
curl https://pyenv.run | bash
```
o

```bash
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
```

**Pegar el código de salida en el archivo `~/.bashrc`, al final**
```bash
# Pyenv configuration

# (The below instructions are intended for common
# shell setups. See the README for more guidance
# if they don't apply and/or don't work for you.)

# Add pyenv executable to PATH and
# enable shims by adding the following
# to ~/.profile:

export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"

# If your ~/.profile sources ~/.bashrc,
# the lines need to be inserted before the part
# that does that. See the README for another option.

# If you have ~/.bash_profile, make sure that it
# also executes the above lines -- e.g. by
# copying them there or by sourcing ~/.profile

# Load pyenv into the shell by adding
# the following to ~/.bashrc:

eval "$(pyenv init -)"

# Make sure to restart your entire logon session
# for changes to profile files to take effect.

# Load pyenv-virtualenv automatically by adding
# the following to ~/.bashrc:

eval "$(pyenv virtualenv-init -)"

```


**Reiniciar el SHELL para que se vean los cambios**
```bash
exec $SHELL
```


```bash

```
