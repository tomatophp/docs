# 👓 Slots

as we like to add more customization to our dashboard we added a new Facade Class TomatoSlot it's used to attach a view to anywhere on the dashboard from any service provider, which means you can create a package to add a button in every single view on the app.

### Use

on your service provider just add

```php
use TomatoPHP\TomatoAdmin\Facade\TomatoSlot;

public function boot()
{        
   TomatoSlot::layoutButtons('core::buttons');
}
```

### Methods

```php
 * @method static navAfterUserDropdown(string $navAfterUserDropdown)
 * @method static navBeforeUserDropdown(string $navBeforeUserDropdown)
 * @method static navLeftSide(string $navLeftSide)
 * @method static sidebarTop(string $sidebarTop)
 * @method static sidebarBottom(string $sidebarBottom)
 * @method static footer(string $footer)
 * @method static dashboardBottom(string $dashboardBottom)
 * @method static dashboardTop(string $dashboardTop)
 * @method static layoutButtons(string $layoutButtons)
 * @method static layoutTitle(string $layoutTitle)
 * @method static layoutTop(string $layoutTop)
 * @method static layoutBottom(string $layoutBottom)
 * @method static layoutButtoms(string $layoutButtoms)
 * @method static logoSection(string $logoSection)
```
