# 🦸‍♂️ Send to Selected User

you can send a notification to a selected user webhook by adding a column on your user table with the name `webhook` and then add this tait to the User model

```php
use TomatoPHP\FilamentDiscord\Traits\InteractsWithDiscord;

class User {
    use InteractsWithDiscord;
}
```

and now you can send notifications to the user like this

```php
use \Filament\Notifications\Notification;

Notification::make()
    ->title('Hi')
    ->body('Welcome On The Moon!')
    ->sendToDiscord($user)
```
