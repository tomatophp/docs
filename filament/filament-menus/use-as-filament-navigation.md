# ⏩ Use as Filament Navigation

you can use this package as a navigation on the Filament Admin Panel

```php
use Filament\Navigation\NavigationBuilder;
use Filament\Navigation\NavigationGroup;
use TomatoPHP\FilamentMenus\FilamentMenuLoader;

$panel->navigation(function (NavigationBuilder $builder){
    return $builder
        // Use Inside Group
        ->groups([
            NavigationGroup::make()
                ->label('Dashboard')
                ->items(FilamentMenuLoader::make('dashboard')),
        ])
        // Use Directly
        ->items(FilamentMenuLoader::make('dashboard'));
})
```

where `dashboard` is a key of menu.

\
