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

after installation use this command to install the package and publish assets

```
php artisan tomato-roles:install
```

### Prepare Your Model

to make your model accept roles you must add this trait to it

```
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;
    
```

### Using

you can use the package by GUI and you can generate new permission by setting the permission name to the route name after that use `tomato-roles.php` config to set the custom permission you need for this route when you add a new one you will get the new permission when you edit the role or add a new and the package will auto-create the permission for you.

if you need to build full resource permission when you use [Tomato Admin](https://github.com/queents/tomato-admin) you can use this command and it will auto-generate it for you

```
php artisan tomato:roles
```

and just gave it the name of the table.

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-roles/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-roles/blob/master/LICENSE.md) for more information.
