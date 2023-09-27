# Use

this plugin make it easy to make a start point of your app if this app has a customers to manage

but here is the problem, every app has a different way to manage customers, so we build a Facade service to control the way you want to manage your customers

### How to use

just install the package and you will get everything working, it's support some features ready to use:

- Accounts
- Groups
- Locations
- Contact Us
- Send Notifications
- Auth APIs
- Send OTP Events

you can activate or deactive any feature as you want form the package config file.

### Use a custom form view for edit or create accounts

you can use your own create / update form for accounts, by just pass the view you when to this facade service method

```php
use TomatoPHP\TomatoCrm\Facades\TomatoCrm;

public function boot()
{
    TomatoCrm::create(form: 'accounts.form');
    TomatoCrm::edit(form: 'accounts.form');
}
```

## Custom create / edit validation

you can custom the validation rules for create / edit accounts by just pass the rules you want to the facade service method

```php

use TomatoPHP\TomatoCrm\Facades\TomatoCrm;

public function boot()
{
    TomatoCrm::validation(
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

by use this method you can custom the validation rules for create / edit accounts on web and APIs


## Attach New Field To Accounts

you can attach new field to accounts table by just pass the field name and the field type to the facade service method

```php

use TomatoPHP\TomatoCrm\Facades\TomatoCrm;

public function boot()
{
    TomatoCrm::attach(
        key: 'birthday',
        label: __('Birthday'),
        type: 'date',
        show_on_create: false,
        show_on_edit: false
    );
}
```