# 📐 Use

this plugin makes it easy to make a starting point for your app if this app has customers to manage

but here is the problem, every app has a different way of managing customers, so we built a Facade service to control the way you want to manage your customers

### How to use

just install the package and you will get everything working, it supports some features ready to use:

* Accounts
* Groups
* Locations
* Contact Us
* Send Notifications
* Auth APIs
* Send OTP Events

you can activate or deactivate any feature you want from the package config file.

### Use a custom form view to edit or create accounts

you can use your own create / update form for accounts, by just passing the view you when to this facade service method

```php
use TomatoPHP\TomatoCrm\Facades\TomatoCrm;

public function boot()
{
    TomatoCrm::create(form: 'accounts.form');
    TomatoCrm::edit(form: 'accounts.form');
}
```

## Custom create / edit validation

you can custom the validation rules for creating / editing accounts by just passing the rules you want to the facade service method

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

by using this method you can custom the validation rules for creating / editing accounts on the web and APIs

## Attach New Field To Accounts

you can attach a new field to the accounts table by just passing the field name and the field type to the facade service method

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


## Publish Model

you can publish the account model to your app by just running this command

```bash
php artisan vendor:publish --tag=tomato-crm-model
```