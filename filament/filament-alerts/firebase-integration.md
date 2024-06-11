# 🔥 Firebase Integration

to make FCM Notification Work you need to install [Filament Settings Hub](https://www.github.com/tomatophp/filament-settings-hub) and allow the use of Setting Hub on the Plugin

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make()
    ->useSettingHub()
    ->useFCM()
)
```

now go to settings hub and update FCM settings by adding admin-auth.json file and update FCM settings then run this command

```bash
php artisan filament-alerts:fcm
```

it will generate FCM worker for you to make notifications working on the background.
