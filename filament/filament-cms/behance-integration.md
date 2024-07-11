# 🏩 Behance Integration

first of all, you need to install `dusk` as a main package to allow this feature

```bash
composer require laravel/dusk
```

now install the dusk driver

```bash
php artisan dusk:install
```

now you need to allow Behance import on your panel provider `/app/Providers/Filament/AdminPanelProvider.php` add this method

```php
->plugin(\TomatoPHP\FilamentCms\FilamentCMSPlugin::make()->allowBehanceImport())
```
