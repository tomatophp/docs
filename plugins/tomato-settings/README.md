---
description: >-
  Full Settings Generator / Manager with GUI for TomatoPHP build with Splade
  build with Laravel-settings
---

# ⚙ Tomato Settings

<figure><img src="../../.gitbook/assets/screenshot (29).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-settings
```

after installation use this command to install the package and publish assets

```
php artisan tomato-settings:install
```

### Using

you can generate a new setting for this package by using this command

```
php artisan tomato:setting
```

it will ask you for the setting name and if you like to put it inside a module as HMVC.

after running the command you must register the menu on the `tomato-admin` config or Module provider.

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-settings/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Credits

* [Queen Tech Solutions](https://github.com/queents)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-settings/blob/master/LICENSE.md) for more information.
