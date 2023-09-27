---
description: full CMS System to manage your content build for Tomato PHP
---

# 📃 Tomato CMS

<figure><img src="../../.gitbook/assets/screenshot (2).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-cms
```

after installing your package please run this command

```
php artisan tomato-cms:install
```

### Publish Assets

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-cms-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-cms-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-cms-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-cms-migrations"
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-cms/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-cms/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-cms/blob/master/LICENSE.md) for more information.
