# osx-config

## Install OSX

### Homebrew


	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	brew tap homebrew/php
	
### Apps

	brew install cask zsh php70 ansible
	brew cask install iterm2 google-chrome phpstorm firefox opera spotify mou virtualbox vagrant slack transmission istat-menus google-drive unrarx

### Shell

	sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
	git clone git://github.com/tlhunter/vimrc.git .vim && ln -s ~/.vim/vimrc ~/.vimrc
	mkdir ~/projects
	
	sh -c "$(curl -fsSL https://raw.githubusercontent.com/powerline/fonts/master/install.sh)"			
	
	click "raw" https://github.com/powerline/fonts/blob/master/Meslo/Meslo%20LG%20M%20DZ%20Regular%20for%20Powerline.otf + install font + select it in iterm2
	
	https://raw.githubusercontent.com/lesmyrmidons/dotfiles/master/gitconfig + modifier content and copy 
	
	echo "$(curl -fsSL https://raw.githubusercontent.com/lesmyrmidons/dotfiles/master/gitconfig)" > ~/.gitconfig
	
	vim ~/.zshrc

Et y ajouter/modifier:


	export PATH="$(brew --prefix homebrew/php/php70)/bin:$PATH"
	
	ZSH_THEME="agnoster"
	
	plugins=(ant boot2docker brew brew-cask bundler capistrano colored-man-pages composer cp docker docker-compose gem git github gitignore gulp man node npm pip python rsync ssh-agent sudo symfony2 themes vagrant xcode history osx sudo systemadmin zsh_reload zsh-navigation-tools)

	# Load xdebug Zend extension with php command
	alias php='php -dzend_extension=xdebug.so'
	# PHPUnit needs xdebug for coverage. In this case, just make an alias with php command prefix.
	alias phpunit='php $(which phpunit)'

Puis :

	curl -sS https://getcomposer.org/installer | php
	mv composer.phar /usr/local/bin/composer
	# Create token here : https://github.com/settings/tokens
	composer config -g github-oauth.github.com ...

### Vagrant / Ansible

	vagrant plugin install vagrant-hostsupdater

### Clé SSH

	ssh-keygen -t dss
	cat ~/.ssh/id_dsa.pub (pour bitbucket)

### Projects

git clone git@bitbucket.org:.../....git ~/projects/...

## Pratiques

## Activer le Proxy
	sudo networksetup -setsocksfirewallproxy "Wi-Fi" localhost 8080 && ssh (user@ip) -D 8080
	
Note : pour voir les noms des devices disponibles :
 
 	networksetup -listallnetworkservices
 	
## Desactiver le Proxy :

	exit (depuis la session SSH ouverte)
	sudo networksetup -setsocksfirewallproxystate "Wi-Fi" off

## A tester :

curl -sL https://raw.githubusercontent.com/egalpin/apt-vim/master/install.sh | sh
apt-vim install -y https://github.com/scrooloose/nerdtree.git
apt-vim install -y https://github.com/yegappan/mru.git
git clone git://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_basic_vimrc.sh
	

