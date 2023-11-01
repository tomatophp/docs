# 💽 Config

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-cms-config"
```

you can publish view files by using this command

```
php artisan vendor:publish --tag="tomato-cms-views"
```

you can publish language files by using this command

```
php artisan vendor:publish --tag="tomato-cms-lang"
```

you can publish migration files by using this command

```
php artisan vendor:publish --tag="tomato-cms-migrations"
```

### Config File

```php
<?php

return [
    "sections_buttons" => null,
    "behance_username" => null,
    "behance_service_id" => null,
    "youtube_key" => null
];
```

you can add more buttons to the index of the section by just passing a blade path to the `sections_buttons`&#x20;

&#x20;our CMS supports data crawling to collect data from other platforms, using dusk, so you can set your `behanace_username` to the config and we will find your projects&#x20;

as you can see there is a types of posts like open-source it's take a data from GitHub if you passing a repo name

and a videos type that's take the data from youtube, but it's need a key
