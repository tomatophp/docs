# 🚀 Install

<figure><img src="../.gitbook/assets/screenshot (14).png" alt=""><figcaption></figcaption></figure>

you can create a new project with our kit or use this package [Tomat Admin](broken-reference)

```
composer create-project tomatophp/tomato
```

create a new database and add your database credentials to .env file

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=tomato-kit
DB_USERNAME=root
DB_PASSWORD=26111995
```

change the main URL in .env file

```
APP_URL=https://tomato-kit.test
APP_HOST=tomato-kit.test
```

clear cache of config

```
php artisan config:cache
```

and run the migration

```
php artisan migrate
```

install frontend packages

```
yarn
yarn build
```

now your app is ready to login `admin/login`

you can use `admin@admin.com` and `password` as a username and password for admin.

enjoy it 🍅

## Using Docker? no problem

if you are using docker as your development env you can up the project in a very easy way by just using this command

```bash
bin/serve
```

The `bin/serve` script is for installing the dependencies and setting up the local environment.\
The only requirement beforehand is that Docker/Docker Desktop is installed.

### Run WebSocket

you can run your socket server just by running this command without any config

```bash
php artisan websocket:serve
```

### Ubuntu Auto Install Script

if you have a fresh install Ubuntu OS you can install all needs for Tomato by just using 1 line

```
ubuntu-22-install-script
```

it will start the install script and ask you for your root password.

### Allow Spatie Media Library inside your app

if you want to use media features inside your app you need to complete setup of Spatie Media Library, it's easy just publish the migration and migrate it.

```bash
php artisan vendor:publish --provider="Spatie\MediaLibrary\MediaLibraryServiceProvider"
```

now run your migration

```bash
php artisan migrate
```

now it's time to allow modules on your app by just adding this line to composer.json

```json
"autoload": {
    "psr-4": {
        ...
        "Modules\\" : "Modules/"
    }
},
```

### Installed Plugins

* [Tomato Splade](https://splade.dev/)
* [Tomato Admin](https://github.com/tomatophp/tomato-admin)
* [Tomato Roles](../plugins/tomato-roles/)
* [Tomato Translations](../plugins/tomato-translations.md)
* [Tomato Logs](../plugins/tomato-logs.md)
* [Tomato Backup](../plugins/tomato-backup.md)

### More Plugins

* [Tomato Plugins](https://docs.tomatophp.com/plugins)

to install this package you can use this command line

```
php artisan tomato:plugins
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Credits

* [Fady Mondy](https://github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato/blob/master/LICENSE.md) for more information.
