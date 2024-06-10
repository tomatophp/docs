# 🏗️ Installation

```
composer require tomatophp/filament-menus
```

after installing your package please run this command

```
php artisan filament-menus:install
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugins(
    \Filament\SpatieLaravelTranslatablePlugin::make()->defaultLocales(['en', 'ar'])
    \TomatoPHP\FilamentMenus\FilamentMenusPlugin::make()
)
```

