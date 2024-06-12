# 🏗️ Installation

```bash
composer require tomatophp/filament-browser
```

after installing your package please run this command

```bash
php artisan filament-browser:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentBrowser\FilamentBrowserPlugin::make())
```
