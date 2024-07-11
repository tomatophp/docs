# 🎭 Theme Manager

the theme manager is built with Laravel Modules so you need to install it first

**Note:** if you are install `tomatophp/filament-plugins` you don't need to install `nwidart/laravel-modules` because it's already installed

```bash
composer require nwidart/laravel-modules
```

now on your `composer.json` add to `psr-4` autoload

```json
{
    "autoload": {
        "psr-4": {
            "App\\": "app/",
            "Modules\\": "Modules/"
        }
    }
}
```

now run this command to autoload themes

```bash
composer dump-autoload
```

and you need another package for caching and return themes as the model we use `sushi` package

```bash
composer require calebporzio/sushi
```

now on your config `filament-cms`

```php
<?php

return [
    /*
     * ---------------------------------------------------
     * Allow Features
     * ---------------------------------------------------
     */
    "features" => [
        "theme-manager" => true,
    ],
];
```

now you need to active the settings table

```bash
php artisan vendor:publish --provider="Spatie\LaravelSettings\LaravelSettingsServiceProvider" --tag="migrations"
php artisan migrate
```

now you can use Theme Manager to manage multi-frontend themes on your app, on your panel provider `/app/Providers/Filament/AdminPanelProvider.php` add this method

```php
->plugin(\TomatoPHP\FilamentCms\FilamentCMSPlugin::make()->useThemeManager())
```

now you can access `/admin/themes` to manage your themes and you can create new themes use this command line

```bash
php artisan filament-cms:theme
```

you will find a new module with a custom `module.json` file on your `Modules` directory

