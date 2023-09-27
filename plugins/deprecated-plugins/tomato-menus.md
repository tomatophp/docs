---
description: Menus manager to build your menus with json file or database provider
---

# 📖 Tomato Menus

<figure><img src="../../.gitbook/assets/screenshot (8).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-menus
```

after install your package please run this command

```
php artisan tomato-menus:install
```

### Publish Assets

you can publish config file by use this command

```
php artisan vendor:publish --tag="tomato-menus-config"
```

you can publish views file by use this command

```
php artisan vendor:publish --tag="tomato-menus-views"
```

you can publish languages file by use this command

```
php artisan vendor:publish --tag="tomato-menus-lang"
```

you can publish migrations file by use this command

```
php artisan vendor:publish --tag="tomato-menus-migrations"
```

## Use Menu Provider

you can use the menu provider on anywhere by our menu provider class it will return your menu anywhere on the app just use

```php
use TomatoPHP\TomatoMenus\Services\MenuRenderBase;

MenuRenderBase::menu($key, $by = 'key');
```

or you can use it with your tomato admin panel by setting the config of menu\_provider to be&#x20;

```php
    "menu_provider" => TomatoPHP\TomatoMenus\Services\MenuRenderBase::class
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-menus/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-menus/blob/master/SECURITY.md) for more information about security.

### Credits

* [Fady Mondy](https://github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-menus/blob/master/LICENSE.md) for more information.

<details>

<summary></summary>



</details>

\
