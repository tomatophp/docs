# ⏯️ Using

### Add Custom Type to CMS

you can add a custom type to the CMS by using the Facade method on your AppServiceProvider `boot()` method

```php
use TomatoPHP\FilamentCms\Facades\FilamentCMS;
use TomatoPHP\FilamentCms\Services\Contracts\CmsType;

public function boot()
{
    FilamentCMS::types()->register([
        CmsType::make('building')
            ->label('Buildings')
            ->icon('heroicon-o-home')
            ->color('danger')
    ]);
}
```

### Add More Authors Types

you can add more author types by using the Facade method on your AppServiceProvider `boot()` method

```php
use TomatoPHP\FilamentCms\Facades\FilamentCMS;
use TomatoPHP\FilamentCms\Services\Contracts\CmsAuthor;

public function boot()
{
    FilamentCMS::authors()->register([
        CmsAuthor::make('Admin')
            ->model(\App\Models\User::class)
    ]);
}
```
