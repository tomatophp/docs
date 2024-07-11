# ⏯️ Using

you can send notifications to discord with multi-way the first of it is using native FilamentPHP `Notification::class`

```php
use \Filament\Notifications\Notification;

Notification::make()
    ->title('Hi')
    ->body('Welcome On The Moon!')
    ->sendToDiscord()
```

you can attach an image to the message like this

```php
use \Filament\Notifications\Notification;

Notification::make()
    ->title('Hi')
    ->body('Welcome On The Moon!')
    ->sendToDiscord(image: "https://raw.githubusercontent.com/tomatophp/filament-discord/master/arts/3x1io-tomato-discord.jpg")
```
