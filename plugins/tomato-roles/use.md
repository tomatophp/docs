# 📐 Use

to make your model accept roles you must add this trait to it

```php
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;
}
```

### Using

you can use the package by GUI and you can generate new permission by setting the permission name to the route name after that use `tomato-roles.php` config to set the custom permission you need for this route when you add a new one you will get the new permission when you edit the role or add a new and the package will auto-create the permission for you.

if you need to build full resource permission when you use [Tomato Admin](https://github.com/queents/tomato-admin) you can use this command and it will auto-generate it for you

```bash
php artisan tomato:roles
```

and just gave it the name of the table.