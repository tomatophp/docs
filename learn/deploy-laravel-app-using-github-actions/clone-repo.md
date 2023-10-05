# 🔃 Clone Repo

login to your server using your terminal with SSH with the user of a created project&#x20;

```bash
ssh youproject@yourIpAddress
```

If you are using a **password** to log in, the **SSH command** would be:

```bash
ssh -i path_to_your_private_key root@yourIpAddress
```

If you are using a **private key** to log in, the SSH command would be:

Login via **SSH** to the **Server**.

you are on the server user and you can generate an SSH key to link it with your GitHub Project to generate this key use this command line

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

and you can just click enter after finishing you will get a path ending with `.pub` copy the path and then use this command to view the path SSH key content and then copy it

```bash
cat .ssh/rsa.pub
```

where.`ssh/rsa.pub` is the path of your key

now go to your GitHun Repo and on the Settings Tab, select Deploy keys and then add deploy Key and then select a name add your SSH key then save it.

now your server has access to this repo and you can clone it so go back to your server and then on the path of the project it can look like this

```bash
cd /home/yourproject/htdocs/yourproject.com
```

and clone your repo like this

```bash
git clone git@github.com:tomatophp/tomato.git .
```

it will clone the project on the current directory

now it's time to install the composer packages and set up the project .env file follow these steps&#x20;

### Copy .env file

use this command to copy .env.example

```bash
cp .env.example .env
```

now update your details and create a new database from Cloudpanel on the Database Tab create a new database, then add the details of the database to .env

```bash
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=tomato-kit
DB_USERNAME=root
DB_PASSWORD=26111995
```

change the main URL in .env file

```bash
APP_URL=https://yourproject.com
APP_HOST=yourproject.com
```

### Install Composer packages and clean the project

to install composer packages just use this command

```bash
composer install
```

then you can run your project command and the important one is

```bash
php artisan key:generate
php artisan config:cache
php artisan storage:link
php artisan optimize:clear
```

now your app is ready for Frontend assets to make this work you need to install npm

### Install NVM/NPM/Yarn

Install [nvm](https://www.cloudpanel.io/docs/v2/php/guides/nodejs/\(https://github.com/nvm-sh/nvm\)/) with the following command:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
```

Update the current shell environment:

```
source ~/.bashrc
```

Install your required **Node.js** version e.g. **18**:

```
nvm install 18
```

Activate the installed **Node.js** version:

```
nvm use 18
```

Done! Check the **Node.js** version:

```
node -v
```

now you can install Yarn using this command

```bash
npm -g i yarn
```

now you can easily run yarn to build assets

```bash
yarn & yarn build
```

your project is ready now and you can view it on your browser.
