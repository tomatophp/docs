# ✌️ Custom validation

you can custom the validation rules for creating/editing accounts by just passing the rules you want to the facade service method

```php
use TomatoPHP\FilamentAccounts\Facades\FilamentAccounts;

public function boot()
{
    FilamentAccounts::validation(
        create: [
            'email' => 'unique:accounts,email',
            'type_id' => 'required|integer|exists:types,id',
        ],
        edit: [
            'email' => 'sometimes|unique:accounts,email',
            'type_id' => 'sometimes|integer|exists:types,id',
        ],
        api_create: [
            'email' => 'unique:accounts,email',
            'type_id' => 'required|integer|exists:types,id',
        ],
        api_edit: [
            'email' => 'sometimes|unique:accounts,email',
            'type_id' => 'sometimes|integer|exists:types,id',
        ]
    );

}
```

by using this method you can custom the validation rules for creating/editing accounts on the web and APIs
