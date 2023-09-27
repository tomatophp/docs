# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-roles-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-roles-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-roles-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-roles-migrations"
```

## Config File

```php
<?php

return [
    /*
     * Select Default Guard
     */
    "defaults" => [
        "guard" => "web",
    ],
    
    /*
     * Add Custom Permissions
     */
    "custom" => [
        "admin" => [
            "admin",
            "admin.lang",
            "admin.profile.edit",
            "admin.profile.update",
            "admin.profile.password",
            "admin.verification.notice",
            "admin.verification.verify",
            "admin.password.confirm",
            "admin.password.confirm.post",
            "admin.password.update",
            "admin.logout",
        ]
    ],
    
    /*
     * Set Developer Gate Password
     */
    'developer_password' => env('DEVELOPER_PASSWORD', "QTS@2022"),
];

```