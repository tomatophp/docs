# 🏗️ Installation



```
composer require tomatophp/filament-plugins
```

after installing your package please run this command

```
php artisan filament-plugins:install
```

By default, the module classes are not loaded automatically. You can autoload your modules by adding merge-plugin to the extra section:

```
"extra": {
    "laravel": {
        "dont-discover": []
    },
    "merge-plugin": {
        "include": [
            "Modules/*/composer.json"
        ]
    }
},
```

now you need to run this command to autoload your modules

```
composer dump-autoload
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentPlugins\FilamentPluginsPlugin::make())
```

