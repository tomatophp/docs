# 🏗️ Installation

```bash
composer require tomatophp/filament-media-manager
```

publish media lib migration

```bash
php artisan vendor:publish --provider="Spatie\MediaLibrary\MediaLibraryServiceProvider" --tag="medialibrary-migrations"
```

now you can install

```
php artisan filament-media-manager:install
```

finally register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`, if you like to use GUI and Folder Browser.

```php
->plugin(\TomatoPHP\FilamentMediaManager\FilamentMediaManagerPlugin::make())
```

\
