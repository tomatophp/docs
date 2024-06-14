# 🏗️ Installation

```bash
composer require tomatophp/filament-cms
```

after installing your package please run this command

```bash
php artisan filament-cms:install
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentCms\FilamentCMSPlugin::make())
```
