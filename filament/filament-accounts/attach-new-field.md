# 🆕 Attach New Field

you can attach a new field to the accounts table by just passing the field name and the field type to the facade service method

```php
use TomatoPHP\FilamentAccounts\Facades\FilamentAccounts;

public function boot()
{
    FilamentAccounts::attach(
        key: 'birthday',
        label: __('Birthday'),
        type: 'date',
        show_on_create: false,
        show_on_edit: false
    );
}
```
