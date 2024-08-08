# ⏯️ Custom Author Type

you can add more author types by using the Facade method on your AppServiceProvider `boot()` method

```php
use TomatoPHP\FilamentWithdrawals\Services\FilamentWithdrawalFormFields;
use TomatoPHP\FilamentWithdrawals\Services\Contracts\WithdrawalFormFieldType;

public function boot()
{
    FilamentWithdrawalFormFields::register([
        WithdrawalFormFieldType::make('code')
            ->className(CodeEditor::class)
            ->color('warning')
            ->icon('heroicon-s-code-bracket-square')
            ->label('Code Editor'),
    ]);
}
```
