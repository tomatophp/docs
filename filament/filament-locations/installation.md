# 🏗️ Installation

```bash
composer require tomatophp/filament-locations
```

after installing your package please run this command

```bash
php artisan filament-locations:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentLocations\FilamentLocationsPlugin::make())
```
