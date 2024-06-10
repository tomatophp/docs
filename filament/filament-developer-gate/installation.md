# 🏗️ Installation

```bash
composer require tomatophp/filament-developer-gate
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
$panel->plugin(\TomatoPHP\FilamentDeveloperGate\FilamentDeveloperGatePlugin::make())
```
