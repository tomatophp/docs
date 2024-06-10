# ®️ List your package on the plugins list

you can list your package on the plugins list by adding this a JSON file in your package root folder with the name `filament-plugin.json` with content like this:

```php
{
    "name": "FilamentAccounts",
    "alias": "filament-accounts",
    "description": {
        "ar": "full accounts manager with API\/Notifications\/Contacts to manage your contacts and accounts",
        "en": "full accounts manager with API\/Notifications\/Contacts to manage your contacts and accounts",
        "gr": "full accounts manager with API\/Notifications\/Contacts to manage your contacts and accounts",
        "sp": "full accounts manager with API\/Notifications\/Contacts to manage your contacts and accounts"
    },
    "keywords": [],
    "priority": 0,
    "providers": [
        "TomatoPHP\\FilamentAccounts\\FilamentAccountsServiceProvider"
    ],
    "files": [],
    "title": {
        "ar": "Filament Accounts",
        "en": "Filament Accounts",
        "gr": "Filament Accounts",
        "sp": "Filament Accounts"
    },
    "color": "#007dff",
    "icon": "heroicon-c-user-circle",
    "placeholder": "placeholder.webp",
    "type": "lib",
    "version": "v1.0",
    "github" : "https://github.com/tomatophp/filament-accounts",
    "docs" : "https://github.com/tomatophp/filament-accounts"
}
```

make sure you allow packages to scan on the `filament-plugins.php` config file

```php
'scan' => true
```
