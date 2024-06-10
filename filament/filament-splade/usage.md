# ⏯️ Usage

to make any page or resource interact with Splade you just need to use this trait

```
use TomatoPHP\FilamentSplade\Traits\InteractsWithSplade;
```

now you can use any splade component inside your resource.

if you like to use Splade everywhere register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentSplade\FilamentSpladePlugin::make())
```

and make sure that you are `global_allow => true` on the config file.

### Register Splade Exceptions

on your `boostrap/app.php` file add this line

```php
->withExceptions(function (Exceptions $exceptions) {
    $exceptions->renderable(function (\Illuminate\Foundation\Exceptions\Handler $e) {
        return \ProtoneMedia\Splade\SpladeCore::exceptionHandler($e);
    });
})
```
