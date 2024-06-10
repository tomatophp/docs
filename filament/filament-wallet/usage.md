# ⏯️ Usage

you need first publish the Account Model using this command

```
php artisan vendor:publish --tag="filament-wallet-model"
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

you can get more details about how to use this package in [Bavix Wallet](https://github.com/bavix/laravel-wallet)

\
