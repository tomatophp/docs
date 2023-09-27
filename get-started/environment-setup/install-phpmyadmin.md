# 🎟 Install PHPMyAdmin

the valet has been installed now, let's go and install PHPMyAdmin and link it with the .test subdomain using valet first of all, create a folder for your sites on the home directory \~

```bash
cd ~
mkdir Sites
cd Sites
```

now we are on the Sites path, let's park this directory to be the directory of our projects

```bash
valet park
```

now any project on this directory will be auto-linked with subdomain .test, let's download PHPMyAdmin from this [link](https://www.phpmyadmin.net/) and unzip the file inside the Sites directory and rename the folder to PHPMyAdmin, after that go inside the folder and use this command

```bash
cp config.sample.inc.php config.sample.php
nano config.sample.php
```

change the line to

```php
$cfg['blowfish_secret'] = 'YK07LhNSe50vrj,HwBfb.l3gpbv;u8b7',
```

now use CTRL + x and say Y now we will use valet to link PHPMyAdmin and secure the link with SSL

```bash
valet link
valet secure
valet open
```

now you can see the PHPMyAdmin working and you can use root as the user and the password you created to MySQL to login
