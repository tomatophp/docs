# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-support-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-support-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-support-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-support-migrations"
```

## Config File

```php
<?php

use TomatoPHP\TomatoSupport\Transformers\FAQResource;
use TomatoPHP\TomatoSupport\Transformers\PagesResource;
use TomatoPHP\TomatoSupport\Transformers\TicketsResource;
use TomatoPHP\TomatoSupport\Transformers\TicketResource;

return [
    /*
     * Add Actions Buttons to the Show Ticket Page with blade view
     */
    "actions" => null,

    /*
     * Show Create Button on Tickets Page
     */
    "show_create_ticket_button" => true,


    /*
     * Resources Classes
     */
    "resources" => [
        "tickets" => [
            "index" => TicketsResource::class,
            "show" => TicketResource::class
        ],
        "pages" => [
            "index" => PagesResource::class,
            "show" => PagesResource::class
        ],
        "faq" => [
            "index" => FAQResource::class,
            "show" => FAQResource::class
        ]
    ],

    /*
     * Features
     */
    "features" => [
        "faq" => true,
        "pages" => true,
        "tickets" => true,
        "apis" => true
    ]
];
```