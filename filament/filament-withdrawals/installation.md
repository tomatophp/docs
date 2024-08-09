# 🏗️ Installation

```bash
composer require tomatophp/filament-withdrawals
```

after install your package please run this command

```bash
php artisan filament-withdrawals:install
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentWithdrawals\FilamentWithdrawalsPlugin::make())
```