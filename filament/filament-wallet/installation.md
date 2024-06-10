# 🏗️ Installation

```
composer require tomatophp/filament-wallet
```

after installing your package please run this command

```
php artisan filament-wallet:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentWallet\FilamentWalletPlugin::make())
```
