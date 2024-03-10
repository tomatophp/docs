---
description: Backup plugin for TomatoPHP build with spatie laravel-backup
---

# 🎒 Tomato Backup

<figure><img src="../.gitbook/assets/screenshot (5).png" alt=""><figcaption></figcaption></figure>

### Before Installation

this package requires sqlite3 ex of PHP to work so please install it&#x20;

On Linux use this command&#x20;

```bash
sudo apt-get install php8.2-sqlite3
```

### Installation

```
composer require tomatophp/tomato-backup
```

or as Module

```
composer require tomatophp/tomato-backup-module
```

after that use this command to install

```
php artisan tomato-backup:install
```

### Markdown Editor Install

we need a markdown editor to make this package work fine, let's start by installing it

```bash
yarn add md-editor-v3
```

now on your app.js add this code

```javascript
import { MdEditor, MdPreview } from 'md-editor-v3';
import 'md-editor-v3/lib/style.css';

createApp({
    render: renderSpladeApp({ el }),
})
    .use(SpladePlugin, {
        max_keep_alive: 10,
        transform_anchors: false,
        progress_bar: true,
    })
    ...
    .component("MdEditor",  MdEditor)
    .component("MdPreview", MdPreview)
    .mount(el);
```

now your markdown editor is ready.

now rebuild your frontend

```bash
yarn build
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-backup/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-backup/blob/master/SECURITY.md) for more information about security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-backup/blob/master/LICENSE.md) for more information.

<details>

<summary></summary>



</details>

\
