# 🏗️ Installation

```bash
composer require tomatophp/filament-ecommerce
```

after installing your package please run this command

```bash
php artisan filament-ecommerce:install
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentEcommerce\FilamentEcommercePlugin::make())
```
