# 🍫 Use Account Column

[![Account Column](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/account-column.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/account-column.png)

you can use the account column in any table by using this code

```php
public static function table(Table $table): Table
{
    return $table
        ->columns([
            AccountColumn::make('account.id'),
        ]);
}
```

just pass the account id to the column
