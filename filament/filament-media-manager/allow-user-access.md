# 🦸‍♂️ Allow User Access

now you can allow users to access selected folders and restrict user to access each other folders if the folder is not public on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(
    \TomatoPHP\FilamentMediaManager\FilamentMediaManagerPlugin::make()
        ->allowUserAccess()
)
```

now on your user model, you can use this trait to allow the user to access the selected folder

```php
use TomatoPHP\FilamentMediaManager\Traits\InteractsWithMediaFolders;

class User extends Authenticatable
{
    use InteractsWithMediaFolders;
}
```

**NOTE** don't forget to migrate after updating the plugin
