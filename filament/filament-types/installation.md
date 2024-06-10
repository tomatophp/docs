# 🏗️ Installation

```bash
composer require tomatophp/filament-types
```

after installing your package please run this command

```bash
php artisan filament-types:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentTypes\FilamentTypesPlugin::make())
```
