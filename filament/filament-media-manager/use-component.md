# ⏯️ Use Component

you can use the media manager by add this code to your filament component

```php
use TomatoPHP\FilamentMediaManager\Form\MediaManagerInput;

public function form(Form $form)
{
    return $form->schema([
        MediaManagerInput::make('images')
            ->disk('public')
            ->schema([
                Forms\Components\TextInput::make('title')
                    ->required()
                    ->maxLength(255),
                Forms\Components\TextInput::make('description')
                    ->required()
                    ->maxLength(255),
            ]),
    ]);
}
```
