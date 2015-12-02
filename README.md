# Ubuntu Boilerplate
This script is intended to set up an Ubuntu box for development with all my preferences and configurations.  It instsall things like git, htop, build-essential, my dotfiles, and some commonly used programming languages.

```bash
#!/bin/bash

# udpate and upgrade aptitude
sudo apt-get update -y
sudo apt-get upgrade -y

# system essentials
sudo apt-get install postfix -y
sudo apt-get install tree -y
sudo apt-get install default-jre -y
sudo apt-get install exuberant-ctags -y
sudo apt-get install build-essential -y

# git, htop
sudo apt-get install git -y
sudo apt-get install git-extras -y
sudo apt-get install htop -y

# python / pip
sudo apt-get install python-pip -y
sudo apt-get install python-dev -y
sudo pip install --upgrade pip
sudo pip install --upgrade virtualenv
sudo pip install --upgrade ohmu

# node / npm
wget https://raw.githubusercontent.com/isaacs/nave/master/nave.sh
sudo bash nave.sh usemain $(sudo bash nave.sh stable)
rm -f nave.sh

# extensions
sudo npm install forever -g
sudo npm install serve -g
sudo npm insatll js-beautify -g
sudo npm install jscs -g
sudo npm install nixar -g

# install dotfiles
git clone git@github.com:wellsjo/dotfiles.git ~/.dotfiles
source ~/.dotfiles/bash/profile
wells_install
```

### Install
```bash
wget https://raw.githubusercontent.com/wellsjo/ubuntu-boilerplate/master/start;
chmod +x start && ./start && rm -f start

```
