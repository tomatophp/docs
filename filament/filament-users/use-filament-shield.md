# 🛡️ Use Filament Shield

you can use the shield to protect your resources and allow user roles by installing it first

```
composer require bezhansalleh/filament-shield
```

Add the Spatie\Permission\Traits\HasRoles trait to your User model(s):

```
use Illuminate\Foundation\Auth\User as Authenticatable;
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;

    // ...
}
```

Publish the config file then set your configuration:

```
->plugin(\BezhanSalleh\FilamentShield\FilamentShieldPlugin::make())
```

Now run the following command to install the shield:

```
php artisan shield:install
```

now on your `filament-users.php` config allows shield

```
/*
 * User Filament Shield
 */
"shield" => true,
```

now clear your config

```
php artisan config:cache
```

for more information check the [Filament Shield](https://github.com/bezhanSalleh/filament-shield)
