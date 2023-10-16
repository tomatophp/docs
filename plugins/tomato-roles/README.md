---
description: >-
  ACL Roles / Permissions for TomatoPHP build with Splade build with
  Laravel-permission
---

# 🔓 Tomato Roles

<figure><img src="../../.gitbook/assets/screenshot (18).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-roles
```

to make your model accept roles you must add this trait to it

```php
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;
}
```

after installation use this command to install the package and publish assets

```
php artisan tomato-roles:install
```

now you can access the `/admin` by using&#x20;

```bash
email: admin@admin.com
password: password
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-roles/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-roles/blob/master/LICENSE.md) for more information.
