---
description: Laravel Dusk unit test with GUI for Tomato Framework
---

# 🧪 Tomato Dusk

<figure><img src="../../.gitbook/assets/screenshot (9).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-dusk
```

after install use this command to install dusk

```
php artisan tomato-dusk:install
```

### Using

it's very easy to use just use this command

```
php artisan tomato:test
```

it will ask you about the test case name and it will generate a test class on path `tests/Browser/Tomato`

after you generate it you can add your code and after that register the class on the `tomato-dusk.php` config file and run

```
php artisan config:cache
```

you now can run your test cases by GUI or this command

```
php artisan tomato-dusk:run
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-dusk/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-dusk/blob/master/SECURITY.md) for more information about security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-dusk/blob/master/LICENSE.md) for more information.

<details>

<summary></summary>



</details>

\
