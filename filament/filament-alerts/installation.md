# 🏗️ Installation



before using this package make sure you have installed

* [Filament Spatie Translatable](https://filamentphp.com/plugins/filament-spatie-translatable)
* [Filament Spatie Media Library](https://filamentphp.com/plugins/filament-spatie-media-library)
* [Filament Settings Hub](https://github.com/tomatophp/filament-settings-hub)

```bash
composer require tomatophp/filament-alerts
```

after installing your package please run this command

```bash
php artisan filament-alerts:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make())
```

### Handel User Model

to set up any model to get notifications you

```php
<?php

namespace App\Models;

use Illuminate\Contracts\Auth\MustVerifyEmail;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Foundation\Auth\User as Authenticatable;
use Illuminate\Notifications\Notifiable;
use Laravel\Fortify\TwoFactorAuthenticatable;
use Laravel\Jetstream\HasProfilePhoto;
use Laravel\Sanctum\HasApiTokens;
use Spatie\Permission\Traits\HasRoles;
use TomatoPHP\FilamentAlerts\Traits\InteractsWithNotifications;

class User extends Authenticatable
{
    use HasApiTokens;
    use HasFactory;
    use HasProfilePhoto;
    use Notifiable;
    use TwoFactorAuthenticatable;
    use HasRoles;
    use InteractsWithNotifications;
    ...
```

and you must set the settings for FCM to get real-time notification

### &#x20;Config Database Queue

the notification is run on queue, so you must run the queue worker to send the notifications

```php
php artisan queue:work
```

#### Hide Notifications Resources

to hide the notification resources from the sidebar you can use the plugin method `hideNotificationsResources` like

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make()
    ->hideNotificationsResources()
)
```
