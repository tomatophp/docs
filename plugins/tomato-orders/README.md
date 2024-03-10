---
description: >-
  full ordering and shipping system management with invoices templates for
  TomatoPHP
---

# 🚀 Tomato Orders

<figure><img src="../../.gitbook/assets/screenshot (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 4.34.05 PM (1).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-orders
```

or as Module

```
composer require tomatophp/tomato-orders-module
```

after installing your package please run this command

```
php artisan tomato-orders:install
```

### Add Items & Search Components

now we need to add 2 components to app.js file

```javascript
import TomatoSearch from "../../vendor/tomatophp/tomato-orders/resources/js/TomatoSearch.vue";
import TomatoItems from "../../vendor/tomatophp/tomato-orders/resources/js/TomatoItems.vue";

createApp({
    render: renderSpladeApp({ el })
})
    .use(SpladePlugin, {
        max_keep_alive: 10,
        transform_anchors: false,
        progress_bar: true,
    })
    .component("TomatoSearch", TomatoSearch)
    .component("TomatoItems", TomatoItems)
```

now rebuild your assets

```bash
yarn & yarn build
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-orders/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-orders/blob/master/SECURITY.md) for more information about security.

### Credits

* [Fady Mondy](mailto:info@3x1.io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-orders/blob/master/LICENSE.md) for more information.
