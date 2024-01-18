---
description: >-
  a full frontend/backend e-commerce system built on top of TomatoPHP, with Cart
  functions and ordering functions
---

# 🛍 Tomato Ecommerce

<figure><img src="../../.gitbook/assets/screenshot (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 4.52.57 PM (1).png" alt=""><figcaption></figcaption></figure>

before starting to install tomato-ecommerce make sure that you have this package installed and configured

* [Tomato Admin](broken-reference/)
* [Tomato Roles](../tomato-roles/)
* [Tomato Settings](../tomato-settings/)
* [Tomato Translations](../tomato-translations.md)
* [Tomato Menus](../tomato-menus/)
* [Tomato Category](../tomato-category/)
* [Tomato Notifications](../tomato-notifications/)
* [Tomato Forms](../tomato-forms/)
* [Tomato CRM](../tomato-crm/)
* [Tomato CMS](../tomato-cms/)
* [Tomato Wallet](../tomato-wallet/)
* [Tomato Products](../tomato-products/)
* [Tomato Orders](../tomato-orders/)
* [Tomato Coupons](../tomato-coupons/)
* [Tomato Sections](../tomato-sections/)
* [Tomato Support](../tomato-support/)
* [Tomato Themes](../tomato-themes/)

### Before Installation

Ensure that PHP sodium extension is enabled.

### Steps to Enable Sodium Extension

* Run the following command in the terminal and note the php.ini file path

```
  php --ini
```

Example path: C:\laragon\bin\php\php-8.1.10-Win32-vs16-x64\php.ini

* Locate and open the php.ini file in a text editor.
* Find the line containing `extension=sodium` and uncomment it by removing the semicolon (;) at the beginning.
* Save the file and restart your PHP environment.

Now, the sodium extension should be active for your PHP installation.

### Installation

```
composer require tomatophp/tomato-ecommerce
```

after installing your package please run this command

```
php artisan tomato-ecommerce:install
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-ecommerce/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-ecommerce/blob/master/SECURITY.md) for more security information.

### Credits

* [Fady Mondy](mailto:info@3x1.io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-ecommerce/blob/master/LICENSE.md) for more information.
