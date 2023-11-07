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

### Markdown Editor Install

we need a markdown editor to be installed on your front let's start by installing the package

```bash
yarn add md-editor-v3
```

now you need to allow it on your app.js

```javascript
import { MdEditor, MdPreview } from 'md-editor-v3';
import 'md-editor-v3/lib/style.css';

createApp({
    render: renderSpladeApp({ el })
})
    .use(SpladePlugin, {
        max_keep_alive: 10,
        transform_anchors: false,
        progress_bar: true,
    })
    .component("MdEditor", MdEditor)
    .component("MdPreview", MdPreview)
    ...
    .mount(el);
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-cms/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-cms/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-cms/blob/master/LICENSE.md) for more information.
