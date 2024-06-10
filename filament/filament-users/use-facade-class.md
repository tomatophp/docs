# 💼 Use Facade Class

you can use the facade class to attach anything to your user resource, in your provider like this

```php
use TomatoPHP\FilamentUsers\Facades\FilamentUser;

public function boot()
{
    FilamentUser::registerAction(\Filament\Actions\Action::make('update'));
    FilamentUser::registerCreateAction(\Filament\Actions\Action::make('update'));
    FilamentUser::registerEditAction(\Filament\Actions\Action::make('update'));
    FilamentUser::registerFormInput(\Filament\Forms\Components\TextInput::make('text'));
    FilamentUser::registerTableAction(\Filament\Tables\Actions\Action::make('update'));
    FilamentUser::registerTableColumn(\Filament\Tables\Columns\Column::make('text'));
    FilamentUser::registerTableFilter(\Filament\Tables\Filters\Filter::make('text'));
}
```

\
