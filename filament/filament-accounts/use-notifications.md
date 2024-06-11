# 🔔 Use Notifications

to make `->useOTPActivation()` work you need to install [Filament Alets](https://github.com/tomatophp/filament-alets) and allow `->useNotifications()` on the plugin

```php
->plugin(\TomatoPHP\FilamentAccounts\FilamentAccountsPlugin::make()
    ...
    ->useNotifications()
)
```
