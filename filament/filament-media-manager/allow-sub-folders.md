# 📂 Allow Sub Folders

you can create and manage subfolders on your media manager on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(
    \TomatoPHP\FilamentMediaManager\FilamentMediaManagerPlugin::make()
        ->allowSubFolders()
)
```
