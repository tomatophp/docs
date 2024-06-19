# ⏯️ Usage

you can generate API by adding this trait to your resource pages

```php
use TomatoPHP\FilamentApi\Traits\InteractWithAPI;
use \Filament\Resources\Pages\ListRecords;

class ListPosts extends ListRecords
{
    use InteractWithAPI;
}
```

and that's it you can now access your API by `/api/{slug}`

we provide 5 methods:

* GET `/api/{slug}` to list all records `support searching by use search=`
* GET `/api/{slug}/{id}` to get a single record
* POST `/api/{slug}` to create a new record
* PUT `/api/{slug}/{id}` to update record
* DELETE `/api/{slug}/{id}` to delete record

### Custom your API

you can customize your API by overriding this method

```php
// Use to return API JSON Resource on Index/Show/Store/Update
public static function getFilamentAPIResource(): ?string
{
    return null;
}

// Use To Custom Your Route Middleware
public static function getFilamentAPIMiddleware(): array
{
    return config('filament-api.default_middleware');
}

// Use To Change the Endpoint Slug
public static function getFilamentAPISlug(): ?string
{
    return null;
}
```
