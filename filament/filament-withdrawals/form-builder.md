# 🔡 Form Builder

### Add Form Field Type

you can add more fields to the form builder by use this method on your provider.

```php
use TomatoPHP\FilamentWithdrawals\Services\FilamentWithdrawalFormFields;
use TomatoPHP\FilamentWithdrawals\Services\Contracts\WithdrawalFormFieldType;

FilamentWithdrawalFormFields::register([
    WithdrawalFormFieldType::make('code')
        ->className(CodeEditor::class)
        ->color('warning')
        ->icon('heroicon-s-code-bracket-square')
        ->label('Code Editor'),
]);
```

### Use Your Form Builder

after create your form you can use it by `id` like this

```php
use TomatoPHP\FilamentWithdrawals\Services\FilamentWithdrawalFormBuilder;

FilamentWithdrawalFormBuilder::make(1)->build()
```

### Use Form Requests to Submit your form data

you can use form requests to submit your form data by use this method on your provider.

```php
use TomatoPHP\FilamentWithdrawals\Services\FilamentWithdrawalFormBuilder;

FilamentWithdrawalFormBuilder::make(1)->send($data)
```