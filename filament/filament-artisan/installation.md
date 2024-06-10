# 🏗️ Installation

```bash
composer require tomatophp/filament-artisan
```

after installing your package please run this command

```bash
php artisan filament-artisan:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentArtisan\FilamentArtisanPlugin::make())
```
