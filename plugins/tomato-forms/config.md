# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-forms-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-forms-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-forms-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-forms-migrations"
```

## Config File

```php

<?php

return [
    /*
     * Supported Languages
     */
    "lang" => [
        "en" => "English",
        "ar" => "Arabic"
    ],
    
    
    /*
     * Resources for APIs
     */
    "index_resource" => null,
    "show_resource" => null,
    "requests_index_resource" => null,
    "requests_show_resource" => null,
    
    /*
     * Service Type class
     */
    "service_type" => null
];

```