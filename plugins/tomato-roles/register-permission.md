# 🏗 Register Permission

you can register any permission you need in the `AppServiceProvider` in the `register` method, it will be auto-registered when you open create / edit role page.

```php
class AppServiceProvider extends ServiceProvider
{
    /**
     * Register any application services.
     */
    public function register(): void
    {
        if(class_exists(TomatoRoles::class)){
            //Register Permission For Settings
            TomatoRoles::register(Permission::make()
                ->name('admin.settings.notifications.index')
                ->guard('web')
                ->group('settings')
            );
            TomatoRoles::register(Permission::make()
                ->name('admin.settings.notifications.store')
                ->guard('web')
                ->group('settings')
            );
        }
    }
}
```