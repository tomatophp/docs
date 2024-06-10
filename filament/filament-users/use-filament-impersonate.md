# 🔒 Use Filament Impersonate

you can use the impersonate to impersonate the user by installing it first

```
composer require stechstudio/filament-impersonate
```

now on your `filament-users.php` config allow shield

```
/*
 * User Filament Impersonate
 */
"impersonate" => true,
```

now clear your config

```
php artisan config:cache
```

for more information check the [Filament Impersonate](https://github.com/stechstudio/filament-impersonate)
