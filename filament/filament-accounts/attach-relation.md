# 🎌 Attach Relation

you can attach a new relation to the accounts relations manager by just passing the relation class to the facade service method

```php
use TomatoPHP\FilamentAccounts\Facades\FilamentAccounts;

public function boot()
{
    FilamentAccounts::registerAccountRelation([
        AccountOrdersRelationManager::make()
    ]);
}
```
