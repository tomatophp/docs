# ⏯️ Usage

to secure selected resources or page you can use this trait

```php
use TomatoPHP\FilamentDeveloperGate\Traits\InteractWithDeveloperGate;
```

or you can use the middleware directly on your routes like this

```php
Route::middleware([\TomatoPHP\FilamentDeveloperGate\Http\Middleware\DeveloperGateMiddleware::class])->group(function () {
    Route::get('/dashboard', function () {
        return view('dashboard');
    })->name('dashboard');
});
```

you can add a logout action button to your page or resource by using this trait

```php
use TomatoPHP\FilamentDeveloperGate\Traits\DeveloperGateLogoutAction;
```
