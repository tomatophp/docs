# ⏯️ Usage

to add a wallet to your user model on your model add this trait

```php
namespace  App\Models;

use Bavix\Wallet\Interfaces\Wallet;
use Bavix\Wallet\Traits\HasWallet;

class Account extends Model implements Wallet
{
    use HasWallet;
}
```

now your model has a wallet on your resource add this action to your table

```php
use TomatoPHP\FilamentWallet\Filament\Actions\WalletAction;

public function table(Table $table): void
{
    $table->actions([
        WalletAction::make('wallet'),
    ]);
}
```

Now, you can charge the wallet of the user by clicking on the wallet action
