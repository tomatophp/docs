# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-notifications-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-notifications-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-notifications-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-notifications-migrations"
```

## Config File

```php
<?php

use App\Models\User;

return [
    /*
     * Notifications types
     */
    'types' => [
        [
            "name" => "Alert",
            "id" => "alert",
            "color" => "#fff",
            "icon" => "bx bxs-user"
        ],
        [
            "name" => "Info",
            "id" => "info",
            "color" => "#fff",
            "icon" => "bx bxs-user"
        ],
        [
            "name" => "Danger",
            "id" => "danger",
            "color" => "#fff",
            "icon" => "bx bxs-user"
        ],
        [
            "name" => "Success",
            "id" => "success",
            "color" => "#fff",
            "icon" => "bx bxs-user"
        ],
        [
            "name" => "Warring",
            "id" => "warring",
            "color" => "#fff",
            "icon" => "bx bxs-user"
        ],
    ],

    /*
     * Main Provider
     */
    'provider' => "pusher",

    /*
     * Models Accept Notifications
     */
    'models' => [
        "Admins" => User::class,
    ],

    /*
     * Providers List
     */
    'providers' => [
        [
            "name" =>'Email',
            "id" => "email"
        ],
        [
            "name" =>'Slack',
            "id" => "slack",
        ],
        [
            "name" => 'Discord',
            "id" => "discord"
        ],
        [
            "name" => 'FCM Web',
            "id" => "fcm-web"
        ],
        [
            "name" => 'FCM Mobile',
            "id" => "fcm-api"
        ],
        [
            "name" => 'Pusher Web',
            "id" => "pusher-web"
        ],
        [
            "name" => 'Pusher Mobile',
            "id" => "pusher-api"
        ],
        [
            "name" => 'SMS MessageBird',
            "id" => "sms-messagebird"
        ]
    ],

    /*
     * Supported Languages
     */
    "lang" => [
        "ar" => "arabic",
        "en" => "english"
    ]
];

```