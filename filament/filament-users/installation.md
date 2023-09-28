# 🏗 Installation

```
composer require tomatophp/filament-users
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```
$panel->plugin(\TomatoPHP\FilamentUsers\FilamentUsersPlugin::make())
```
