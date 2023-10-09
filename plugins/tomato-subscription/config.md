# 💽 Config

you can publish a config file by using this command

```bash
php artisan vendor:publish --tag="tomato-subscription-config"
```

you can publish view files by use this command

```bash
php artisan vendor:publish --tag="tomato-subscription-views"
```

you can publish language files by use this command

```bash
php artisan vendor:publish --tag="tomato-subscription-lang"
```

you can publish migration files by using this command

```bash
php artisan vendor:publish --tag="tomato-subscription-migrations"
```

## Config File

```php
<?php

return [
    'types' => [
        [
            "label" => "Users",
            "id" => \App\Models\User::class
        ],
    ]
];
```
