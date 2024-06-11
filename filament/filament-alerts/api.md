# ⚙️ API

We support some API to get the notification and make some actions you can find it under `api/notifications` route

you can change the user model by using the plugin method `apiModel` like

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make()
    ->apiModel(User::class)
)
```
