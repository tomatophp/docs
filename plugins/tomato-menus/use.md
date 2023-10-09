# 📐 Use

you can use the menu provider on anywhere by our menu provider class it will return your menu anywhere on the app just use

```php
use TomatoPHP\TomatoMenus\Services\MenuRenderBase;

MenuRenderBase::menu($key, $by = 'key');
```

or you can use it with your tomato admin panel by setting the config of menu\_provider to be&#x20;

```php
"menu_provider" => TomatoPHP\TomatoMenus\Services\MenuRenderBase::class
```
