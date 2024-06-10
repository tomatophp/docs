# ⏯️ Using

to generate a new helper class you can use this command

```bash
php artisan filament:helpers
```

and select the type and name, and you can generate the class inside the module or on the selected path inside your resource.

### Using Generated Class



and you can use the generated class like this

```php
use App\Filament\Resources\AccountResource\Forms\UserForm;

public function form(Form $form): Form
{
    return UserForm::make($form);
}
```

```php
use App\Filament\Resources\AccountResource\Tables\UserTable;

public function form(Table $table): Table
{
    return UserTable::make($table);
}
```

```php
use App\Filament\Resources\AccountResource\Actions\UserActions;

public function table(Table $table): Table
{
    return $table->actions(UserActions::make());
}
```

```php
use App\Filament\Resources\AccountResource\Actions\UserFilters;

public function table(Table $table): Table
{
    return $table->filters(UserFilters::make());
}
```
