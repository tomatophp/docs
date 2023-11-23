# 💿 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-builder-config"
```

you can publish view files by use this command

```
php artisan vendor:publish --tag="tomato-builder-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-builder-lang"
```

you can publish migration files by use this command

```
php artisan vendor:publish --tag="tomato-builder-migrations"
```

## Config File

```php
<?php

return [
    "stubs-path" => "vendor/tomatophp/tomato-builder/src/stubs/",
];
```

you can change the stubs path as you like and build your own templates
