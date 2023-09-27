# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-crm-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-crm-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-crm-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-crm-migrations"
```

## Config File

```php
<?php

use Modules\Base\Transformers\AccountLoginResource;

return [
    /*
     * Features of Tomato CRM
     *
     * accounts: Enable/Disable Accounts Feature
     */
    "features" => [
        "accounts" => true,
        "groups" => true,
        "locations" => false,
        "contacts" => false,
        "activites" => false,
        "notifications" => true,
        "apis" => true,
        "send_otp" => true
    ],

    /*
     * Accounts Configurations
     *
     * resource: User Resource Class
     */
    "resource" => AccountLoginResource::class,

    /*
     * Accounts Configurations
     *
     * login_by: Login By Phone or Email
     */
    "login_by" => "email",

    /*
     * Accounts Configurations
     *
     * required_otp: Enable/Disable OTP Verification
     */
    "required_otp" => true,

    /*
     * Accounts Configurations
     *
     * model: User Model Class
     */
    "model" => \App\Models\Account::class,

    /*
     * Accounts Configurations
     *
     * guard: Auth Guard
     */
    "guard" => "accounts",


    "views" => [
        "accounts" => [
            "buttons" => null,
            "actions" => "base::accounts-actions",
        ]
    ],


    /*
     * Attachment Relations
     *
     * You can use this config to attach relation manager to the view accounts
     *
     * Example:
     *
     [
         "name" => "groups",
         "label" => [
           "ar" => "Group",
           "en" => "Group"
         ],
         "table" => \TomatoPHP\TomatoCrm\Tables\GroupTable::class,
         "view" => "tomato-crm::components.relations",
         "show" => true,
         "edit" => true,
         "delete" => true,
         "path" => "groups"
     ]
     */
    "relations" => [
        [
            "name" => "properties",
            "label" => [
                "ar" => "Properties",
                "en" => "Properties"
            ],
            "table" => \Modules\Unites\Tables\PropertyTable::class,
            "view" => null,
            "show" => true,
            "edit" => true,
            "delete" => true,
            "path" => "properties"
        ]
    ]
];
```
