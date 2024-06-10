# 🔏 Use Filament Impersonate

you can use the impersonate to impersonate the user by installing it first

```bash
composer require stechstudio/filament-impersonate
```

now on your `filament-users.php` config allow shield

```php
"features" => [
    ...
    "impersonate" => [
        'active'=> true,
        'redirect' => '/app',
    ],
],
```

now clear your config

```bash
php artisan config:cache
```

for more information check the [Filament Impersonate](https://github.com/stechstudio/filament-impersonate)
