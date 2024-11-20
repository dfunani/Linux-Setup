# Linux-Setup
Dedicated documentation on the setting up of Linux OS locally.

## Create ssh key 

```bash
ssh-keygen -t rsa -b 4096 -C "unique-key-identifier" -f ~/.ssh/id_rsa
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
```

## Install dependencies

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install zsh git python3-pip -y
```

## Install oh-my-zsh (Pretty Terminal)

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
chsh -s $(which zsh)
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

# Configure Github

```bash
git config --global core.autocrlf input
git config --global core.eol lf
git config --global user.email # email@example.com
git config --global user.name # name-surname
git config --global url."git@github.com:".insteadOf "https://github.com/"
```
