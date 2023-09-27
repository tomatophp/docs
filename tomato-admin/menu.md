# 📖 Menu

it's a very easy-to-use menu provider by just using this class method on your app service provider

```php
use TomatoPHP\TomatoAdmin\Facade\TomatoMenu;
use TomatoPHP\TomatoAdmin\Services\Contracts\Menu;

public function boot()
{
     TomatoMenu::register([
           Menu::make()
            ->group(__('ALC'))
            ->label(__('Users'))
            ->icon('bx bx-user')
            ->route('admin.users.index'),
           Menu::make()
            ->group(__('ALC'))
            ->label(__('Roles'))
            ->icon('bx bx-lock')
            ->route('admin.roles.index')
    ]);
}
```

and the menu will auto registered to your sidebar of the admin dashboard

you can be ordering the groups or hide a group using this method

```php
use TomatoPHP\TomatoAdmin\Facade\TomatoMenu;

public function boot()
{
    TomatoMenu::groups([
        __('ALC') => true,
        __('Settings') => false, //Hidden
    ]);
}
```
