---
description: Build and manage SaaS apps with easy GUI
---

# 🌟 Tomato SaaS

<figure><img src="../../.gitbook/assets/screenshot (30).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-saas
```

after installing your package please run this command

```
php artisan tomato-saas:install
```

### Publish Assets

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-saas-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-saas-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-saas-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-saas-migrations"
```

add this to `config/database.php`

```php
    'dynamic' => [
        'driver' => 'mysql',
        'url' => env('DATABASE_URL'),
        'host' => env('DB_HOST', '127.0.0.1'),
        'port' => env('DB_PORT', '3306'),
        'database' => env('DB_DATABASE', 'forge'),
        'username' => env('DB_USERNAME', 'forge'),
        'password' => env('DB_PASSWORD', ''),
        'unix_socket' => env('DB_SOCKET', ''),
        'charset' => 'utf8mb4',
        'collation' => 'utf8mb4_unicode_ci',
        'prefix' => '',
        'prefix_indexes' => true,
        'strict' => true,
        'engine' => null,
        'options' => extension_loaded('pdo_mysql') ? array_filter([
            PDO::MYSQL_ATTR_SSL_CA => env('MYSQL_ATTR_SSL_CA'),
        ]) : [],
    ]
```

### Support

you can join our discord server to get support [TomatoPHP](https://discord.gg/VZc8nBJ3ZU)

### Docs

you can check docs of this package on [Docs](https://docs.tomatophp.com/plugins/laravel-package-generator)

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-saas/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-saas/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-saas/blob/master/LICENSE.md) for more information.
