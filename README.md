# Linux-Setup
Dedicated documentation on the setting up of Linux OS locally.
mkdir ~/RC

# Create ssh key 
ssh-keygen -t rsa -b 4096 -C "<your-retail-capital-email-address>" -f ~/.ssh/id_rsa
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa

sudo apt update
sudo apt upgrade -y

# Install zsh
sudo apt install zsh -y

# Install oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Set zsh as default shell
chsh -s $(which zsh)

# Install pip
sudo apt install python3-pip

# Install pipenv
# This is used to create a new, isolated environment for each project that you start
pip install pipenv

# Add pipenv auto-activation to .zshrc
echo 'eval "$(pipenv --completion)"' >> ~/.zshrc
echo 'pipenv shell' >> ~/.zshrc

# Ensure that our line ending characters are the same whether on Windows or Linux
git config --global core.autocrlf input
git config --global core.eol lf

# Ensure that SSH is always used
git config --global url."git@github.com:".insteadOf "https://github.com/"

# Install the Powerlevel 10K theme
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
