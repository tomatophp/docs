# 🏗 Installation

```
composer require tomatophp/filament-translations
```

### Publish Resource <a href="#user-content-publish-resource" id="user-content-publish-resource"></a>

you can publish the resource to your project

```
php artisan vendor:publish --tag="filament-translations-migrations"
```

if you need to publish the config

```
php artisan vendor:publish --tag="filament-translations-config"
```

Run migration:

```
php artisan migrate
```

and now clear the cache

```
php artisan optimize:clear
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make())
```
