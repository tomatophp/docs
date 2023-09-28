---
description: Manage your translation with DB and cache
---

# 🌎 Filament Translations

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Manage your translation with DB and cache, you can scan your languages tags like `trans()`, `__()`, and get the string inside and translate them use UI.

this plugin is build in [spatie/laravel-translation-loader](https://github.com/spatie/laravel-translation-loader)

### Installation <a href="#user-content-installation" id="user-content-installation"></a>

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

### Support <a href="#user-content-support" id="user-content-support"></a>

you can join our discord server to get support [TomatoPHP](https://discord.gg/VZc8nBJ3ZU)

### Changelog <a href="#user-content-changelog" id="user-content-changelog"></a>

Please see [CHANGELOG](https://github.com/tomatophp/filament-translations/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security <a href="#user-content-security" id="user-content-security"></a>

Please see [SECURITY](https://github.com/tomatophp/filament-translations/blob/master/SECURITY.md) for more information about security.

### Credits <a href="#user-content-credits" id="user-content-credits"></a>

* [Fady Mondy](mailto:info@3x1.io)

### License <a href="#user-content-license" id="user-content-license"></a>

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/filament-translations/blob/master/LICENSE.md) for more information.
