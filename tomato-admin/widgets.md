# 🌉 Widgets

we build a widget Facade service to make it easy to register a widget to dashboard home page from any provider, so you can use it on your package or on your AppServiceProvider as will.

## Registering a widget

you can go to any service provider `boot()` method and register your widget like this:

```php
use TomatoPHP\TomatoAdmin\Facade\TomatoWidget;
use TomatoPHP\TomatoAdmin\Services\Contracts\Widget;

public function boot()
{
    TomatoWidget::register([
            Widget::make()
                ->title(__('Users'))
                ->icon('bx bxs-user')
                ->counter(User::count()),
            Widget::make()
                ->title(__('Roles'))
                ->icon('bx bx-lock')
                ->counter(Role::count())
        ]);
    }
}
```

and you will see the widget on the homepage of dashboard directly.