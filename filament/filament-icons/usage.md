# ⏯️ Usage

### Use Form Component

you can add form components like this, and it accepts all `Select::class` methods

```php
use TomatoPHP\FilamentIcons\Components\IconPicker;

public static function form(Form $form): Form
{
    return $form
        ->schema([
            IconPicker::make('icon')
                ->default('heroicon-o-academic-cap')
                ->label('Icon'),
        ]);
}
```

### Use Table Column

you can add table columns like this

```php
use TomatoPHP\FilamentIcons\Components\IconColumn;

public static function table(Table $table): Table
{
    return $table
        ->columns([
            IconColumn::make('icon')
                ->label('Icon'),
        ]);
}
```
