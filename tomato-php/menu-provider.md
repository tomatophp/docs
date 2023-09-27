# 📖 Menu Provider

it's a very easy-to-use menu provider by just using this class method on your app service provider

```php
use Queents\TomatoAdmin\Services\Menu\TomatoMenuRegister;

public function boot()
{
    TomatoMenuRegister::registerMenu(UserMenu::class);
}
```

and the menu will auto registered to your sidebar of the admin dashboard

to build a Menu class you can use it like this

```php
<?php

namespace App\Menus;

use Queents\TomatoPHP\Services\Menu\Menu;
use Queents\TomatoPHP\Services\Menu\TomatoMenu;

class UserMenu extends TomatoMenu
{
    /**
     * @var ?string
     * @example ACL
     */
    public ?string $group = "ALC";

    /**
     * @var ?string
     * @example dashboard
     */
    public ?string $menu = "dashboard";

    /**
     * @return array
     */
    public static function handler(): array
    {
        return [
            Menu::make()
                ->label("Users Info")
                ->icon("bx bxs-user")
                ->route("admin.users.index"),
        ];
    }
}
```
