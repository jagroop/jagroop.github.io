# Multiple PHP versions on Ubuntu (Linux)

## Install PHP (5.6, 7.0, 7.1) on Ubuntu Using PPA

```bash
sudo apt install python-software-properties
sudo add-apt-repository ppa:ondrej/php
```

```bash
sudo apt-get update
```

### For Apache Web Server

```bash
sudo apt install php5.6   # [PHP 5.6]
sudo apt install php7.0   # [PHP 7.0]
sudo apt install php7.1   # [PHP 7.1]
```

### For Nginx Web Server

```bash
sudo apt install php5.6-fpm   # [PHP 5.6]
sudo apt install php7.0-fpm   # [PHP 7.0]
sudo apt install php7.1-fpm   # [PHP 7.1]
```
### Install most required PHP modules

```bash
sudo apt install php5.6-cli php5.6-xml php5.6-mysql 
sudo apt install php7.0-cli php7.0-xml php7.0-mysql 
sudo apt install php7.1-cli php7.1-xml php7.1-mysql 
```

### Set Default PHP Version in Ubuntu

```bash
sudo update-alternatives --set php /usr/bin/php5.6

## OR ##

sudo update-alternatives --set php /usr/bin/php7.0

## OR ##

sudo update-alternatives --set php /usr/bin/php7.1
```

### Set the PHP version that will work with Apache web server

To set the PHP version that will work with Apache web server, use the commands below. First disable the current version with the a2dismod command and then enable the one you want with the a2enmod command.

```bash
sudo a2dismod php7.0
sudo a2enmod php7.1
sudo systemctl restart apache2
```

After switching from one version to another, you can find your PHP configuration file, by running the command below.

```bash
------------ For PHP 5.6 ------------
$ sudo update-alternatives --set php /usr/bin/php5.6
$ php -i | grep "Loaded Configuration File"
------------ For PHP 7.0 ------------
$ sudo update-alternatives --set php /usr/bin/php7.0
$ php -i | grep "Loaded Configuration File"
------------ For PHP 7,1 ------------
$ sudo update-alternatives --set php /usr/bin/php7.1
$ php -i | grep "Loaded Configuration File"
```
[Reference Link](https://www.tecmint.com/install-different-php-versions-in-ubuntu/)
