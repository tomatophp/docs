# 🏗️ Installation

```bash
composer require tomatophp/filament-settings-hub
```

now you need to publish and migrate the settings table

```bash
php artisan vendor:publish --provider="Spatie\LaravelSettings\LaravelSettingsServiceProvider" --tag="migrations"
```

after publishing and migrating the settings table please run this command

```bash
php artisan filament-settings-hub:install
```

finally, register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentSettingsHub\FilamentSettingsHubPlugin::make())
```
