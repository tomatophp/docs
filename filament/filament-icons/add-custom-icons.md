# 🪄 Add Custom Icons

you can add a custom icon lib by using this Facade class inside your provider like this

```php
use TomatoPHP\FilamentIcons\Facades\FilamentIcons;

public function boot(): void
{
    FilamentIcons::register('boxicons')
        ->asset('https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css')
        ->template('<i class="{ ICON }"></i>', 'text-xl', 'text-sm')
        ->icons([
            "bx bx-accessibility",
            "bx bx-add-to-queue",
            "bx bx-adjust"
        ])  
        ->replace(['bx ', 'bxs-', 'bxl-', 'bx-'])
        ->save();
}
```

then you need to clear the cache by using this command

```bash
php artisan filament-icons:clear
```

you can try adding Box Icons using this snap [Box Icon Snap](https://github.com/tomatophp/filament-icons/blob/master/boxicons-provider-snap.md)
