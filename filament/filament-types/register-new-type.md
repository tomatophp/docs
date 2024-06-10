# ⏯️ Register New Type

you can add a new type using the config file `config/filament-types.php` or you can register a type from your provider using our Facade

```php
use TomatoPHP\FilamentTypes\Facades\FilamentTypes;

FilamentTypes::register([
    'types',
    'groups'
], 'accounts');
```

\
