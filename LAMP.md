# Ubuntu 16.04 LAMP installation.

## Apache

```bash
sudo apt update
sudo apt install apache2
```

```bash
sudo vim /etc/apache2/apache2.conf
```

```bash
...
ServerName SİZİN_ALAN_ADINIZ_VEYA_IP_ADRESİNİZ
...

```

```bash
sudo apache2ctl configtest
```

```
# Çıktı:
Syntax OK
```

```bash
sudo ufw app list
```

```
# Çıktı:
Available applications:
  Apache
  Apache Full
  Apache Secure
  OpenSSH
```

```bash
sudo ufw app info "Apache Full"
```

```
# Çıktı:
Profile: Apache Full
Title: Web Server (HTTP,HTTPS)
Description: Apache v2 is the next generation of the omnipresent Apache web
server.

Ports:
  80,443/tcp
```

```bash
sudo ufw allow in "Apache Full"
```

```
http://SİZİN_ALAN_ADINIZ_VEYA_IP_ADRESİNİZ
```

## MySQL kurulumu:

```bash
sudo apt-get install mysql-server
sudo mysql_secure_installation
```

## PHP

```bash
sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql
```

```bash
sudo vim /etc/apache2/mods-enabled/dir.conf

```

```
<IfModule mod_dir.c>
    DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
</IfModule>
```

## phpMyAdmin

```bash
sudo apt-get install phpmyadmin php-mbstring php-gettext
sudo phpenmod mcrypt
sudo phpenmod mbstring
```

```bash
sudo systemctl restart apache2
sudo systemctl status apache2

```

```
http://SİZİN_ALAN_ADINIZ_VEYA_IP_ADRESİNİZ/phpmyadmin
```

## Basit php sitesi

```bash
sudo vim /var/www/html/info.php
```

```
<?php
phpinfo();
?>

```

```
http://SİZİN_ALAN_ADINIZ_VEYA_IP_ADRESİNİZ/info.php
```

```
sudo rm /var/www/html/info.php
```

