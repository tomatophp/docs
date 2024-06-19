# 🏗️ Installation



```bash
composer require tomatophp/filament-api
```

if you want to use API Resource to list your generated APIs you can register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentApi\FilamentAPIPlugin::make())
```
