# 💿 Configuring the server

we are recommending using our environment to make the project work will we are using ubuntu Linux and laravel valet +

### Install BackBox Linux

we are like to use [BackBox](https://www.backbox.org/download/) Linux it has a lot of tools and supports our environment, so from the link we keep downloading the ISO image and putting it in USB using [Rufus](https://rufus.ie/en/) and then booting your computer into it

***

### Install dependencies packages

let's start by opening our terminal and updating the system to the last one, and after that install some packages

```bash
sudo add-apt-repository -y ppa:nginx/stable
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
```

```bash
sudo apt-get upgrade
```

after it finished reboot your computer and after that run this command

```bash
sudo apt-get install network-manager libnss3-tools jq xsel
```

***

### Install PHP & its extensions

```bash
sudo apt install php8.2-fpm
```

```bash
sudo apt install php8.2-cli php8.2-common php8.2-curl php8.2-mbstring php8.2-opcache php8.2-readline php8.2-xml php8.2-zip php8.2-mysql php8.2-gd
```

### Install MySql Server

```bash
sudo apt-get -y install mysql-server
```

```bash
sudo mysql_secure_installation
```

use `0` for the password and use any password something like `12345678`

after the installation is finished, start MySQL server

```bash
sudo mysql
```

and on the MySQL server console use this command

```sql
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';
```

```sql
mysql> FLUSH PRIVILEGES;
```

```sql
mysql> exit;
```

***

### Install Composer

```bash
sudo apt install curl
```

```bash
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

