# 🏨 Page Builder

&#x20;

<figure><img src="https://raw.githubusercontent.com/tomatophp/filament-cms/master/arts/page-builder-preview.png" alt=""><figcaption><p>Page Builder Home Page</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/tomatophp/filament-cms/master/arts/page-builder.png" alt=""><figcaption><p>Edit Page</p></figcaption></figure>

the page builder makes it very easy to custom your page and generate autoloaded pages to build your website using `Sections` to start using it you need to add this method to your panel provider `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentCms\FilamentCMSPlugin::make()->usePageBuilder())
```

first thing you need to create a Section on your AppServiceProvider `boot()` method

```php
use TomatoPHP\FilamentCms\Services\Contracts\Section;
use TomatoPHP\FilamentCms\Facades\FilamentCMS;
use Filament\Forms\Components\TextInput;

FilamentCMS::themes()->register([
    Section::make('hero')
        ->label('Hero Section')
        ->view('sections.pages.hero')
        ->form([
            TextInput::make('title')
                ->label('title'),
            TextInput::make('description')
                ->label('description'),
            TextInput::make('url')
                ->url()
                ->label('url'),
            TextInput::make('button')
                ->label('button'),
        ])
]);
```

**NOTE:** the section key must be unique

after registering your section you can start using Page Builder, you need to create a new route for your page like this

```php
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    $page = load_page('/');
    return view('welcome', compact('page'));
});
```

as you see you need to use `load_page` helper to load your page and pass it to your view, this method checks if the page exists by `slug` and return the page data if the page doesn't exists or is deleted it will restore it or create it for you

on your `welcome.blade.php` file you need to use this blade component

```php
<x-tomato-builder-toolbar :page="$page" allow-layout/>
```

if you need to use Filament Layout to make it easy to active Livewire / Tailwind Style use `allow-layout` attribute if you need to use it without any style you can use it without this attribute

now if you open your page you will find the builder view like this
