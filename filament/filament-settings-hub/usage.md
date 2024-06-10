# ▶️ Usage

you can use this package by using this helper function

```php
settings($key);
```

to register new settings to the hub page you can use the Facade class on your provider like this

```php
use TomatoPHP\FilamentSettingsHub\Facades\FilamentSettingsHub;
use TomatoPHP\FilamentSettingsHub\Services\Contracts\SettingHold;

FilamentSettingsHub::register([
    SettingHold::make()
        ->label(__('Site Settings'))
        ->icon('heroicon-o-globe-alt')
        ->route('filament.admin.pages.site-settings')
        ->description(__('Name, Logo, Site Profile'))
        ->group(__('General')),
]);
```

and now you can see your settings on the settings hub page.

we have a ready-to-use helper for currency settings

```php
dollar($amount)
```

it will return the money amount with the currency symbol
