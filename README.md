# Configuração do ambiente

## Instalando pacotes
```shell
sudo apt-get update -y
sudo apt-get dist-upgrade -y

sudo apt-get install -y geany htop vim gimp code composer pidgin zsh dbeaver-ce openjdk-8-jdk-headless openjdk-11-jdk-headless openjdk-14-jdk-headless
```

## Git
```shell
git config --global credential.helper store
git config --global user.name 'Clairton Carneiro Luz'
git config --global user.email clairton.c.l@gmail.com
```

# Trocando bash default para zsh
```shell
grep $USER /etc/passwd
chsh -s $(which zsh)
grep $USER /etc/passwd
```

# OhMyZsh
```shell
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
## edit `~/.zshrc` plugins zsh
```shell
plugins=(
git
asdf
composer
docker
docker-compose
aws
gradle
npm
npx
node
)
```

# Install asdf
```shell
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.0
```

# Install node.js by asdf
```shell
asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git


# Import the Node.js release team's OpenPGP keys to main keyring:
bash -c '${ASDF_DATA_DIR:=$HOME/.asdf}/plugins/nodejs/bin/import-release-team-keyring'

# list all versions
asdf list all nodejs

# install version 14.13.0
asdf install nodejs 14.13.0

# define version active
asdf global nodejs 14.13.0
```

# Install docker

 Siga o tutorial oficial: https://docs.docker.com/engine/install/ubuntu/

docker composer: https://docs.docker.com/compose/install/

## Adicionar ao grupo do docker
 ```shell
 sudo usermod -aG docker $USER
 ```


## habilita docker para iniciar junto com o sistema
 ```shell 
 sudo systemctl enable docker
 ```

# DEBEAVER Add this lines above -vmargs into /usr/share/dbeaver/dbeaver.ini

```ini
	-vm
	/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.232.b09-0.fc31.x86_64/jre/bin/
```

# Editor default
```shell
echo "export EDITOR=$(which vim)" >> ~/.bashrc	
echo "export EDITOR=$(which vim)" >> ~/.zshrc
echo "set number" > ~/.vimrc
echo "set expandtab" >> ~/.vimrc
echo "set autoindent" >> ~/.vimrc
echo "syntax enable" >> ~/.vimrc
echo "set wrap" >> ~/.vimrc
```
# Modifica atalho de mover e trocar de workspace pois os atalhos originais já são usados por algumas IDEs de desenvolvimento

```shel
gsettings set org.gnome.desktop.wm.keybindings move-to-workspace-up "['<Super><Shift>Page_Up']"

gsettings set org.gnome.desktop.wm.keybindings move-to-workspace-down "['<Super><Shift>Page_Down']"

gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-up "['<Super>Page_Up']"

gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-down "['<Super>Page_Down']"
```
