# 🏗️ Installation

```bash
composer require tomatophp/filament-notes
```

after installing your package please run this command

```bash
php artisan filament-notes:install
```

Finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make())
```
