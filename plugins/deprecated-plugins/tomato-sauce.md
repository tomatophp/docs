---
description: a full reports generator plugin to build dashboard reports
---

# 🌭 Tomato Sauce

<figure><img src="../../.gitbook/assets/screenshot (3).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-sauce
```

after installation please run this command

```
php artisan tomato-sauce:install
```

after installation please copy this to your app.js

```
import charts from "../../vendor/tomatophp/tomato-sauce/resources/js/charts.vue";
```

and after `createApp()`

```
.component("charts", charts)
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-sauce/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-sauce/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Khaled Abodaif](https://github.com/khaledAbodaif)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-sauce/blob/master/LICENSE.md) for more information.
