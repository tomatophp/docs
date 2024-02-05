---
description: Full POS system for tomato ordering and inventory
---

# 🧾 Tomato POS



<figure><img src="../../.gitbook/assets/screenshot (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-07 at 6.46.05 PM.png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-pos
```

after installing your package please run this command

```
php artisan tomato-pos:install
```

### Add Style

you need to add style.css to your app.css please on this file `resources/css/app.css` add this line after the imports

```
@import url('../../vendor/tomatophp/tomato-pos/resources/css/style.css');
```

now build your asset

```
yarn && yarn build
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-pos/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-pos/blob/master/SECURITY.md) for more security information.

### Credits

* [Fady Mondy](mailto:info@3x1.io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-pos/blob/master/LICENSE.md) for more information.
