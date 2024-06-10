# 🔘 Attach Table Button

you can attach a new button to the accounts table by just passing the button class to the facade service method

```php
use TomatoPHP\FilamentAccounts\Facades\FilamentAccounts;

public function boot()
{
    FilamentAccounts::registerAccountActions([
        \Filament\Tables\Actions\Action::make('orders')
    ]);
}
```
