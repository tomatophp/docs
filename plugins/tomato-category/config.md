# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-category-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-category-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-category-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-category-migrations"
```

## Config File

```php
<?php

return [
    /*
     * Types For
     * 
     * you may need a types for accounts and another for content
     */
    "for" => [
        "accounts"=> [
            "ar" => "الحسابات",
            "en" => "Accounts"
        ],
        "content"=> [
            "ar" => "المحتوي",
            "en" => "Content"
        ]
    ],
    
    /*
     * Types Of Type
     * 
     * it's a sub-type of type like account type or content type
     */
    "types" => [
        "type"=> [
            "ar" => "النوع",
            "en" => "Type"
        ],
        "status"=> [
            "ar" => "الحالة",
            "en" => "Status"
        ],
    ],
    
    
    /*
     * Features
     */
    "features" => [
        "category" => false,
        "types" => true
    ],
    
    /*
     * Category Middleware
     * 
     * you can add a middleware to the category APIs routes
     */
    "middleware" => [],
    
    /*
     * Category Resource
     * 
     * you can custom API resource for categories
     */
    "categories_resource" => null,
    
    /*
     * Types Resource
     * 
     * you can custom API resource for types
     */
    "types_resource" => null,
];

```