# 🏁 Filament Accounts Integration

first, you need to install Filament Account Builder

```bash
composer require tomatophp/filament-account
```

then you need to publish the model file

```bash
php artisan vendor:publish --tag="filament-accounts-model"
```

then you can use this model in your project and attach this trait to your model

```php
namespace  App\Models;

use Bavix\Wallet\Interfaces\Wallet;
use Bavix\Wallet\Traits\HasWallet;

class Account extends Model implements Wallet
{
    use HasWallet;
}
```

now your account has a balance ready.

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentWallet\FilamentWalletPlugin::make()->useAccounts())
```
