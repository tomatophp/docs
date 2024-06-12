# ⏯️ Usage

you can use the filament native notification and we add some `macro` for you

```php
use Filament\Notifications\Notification;

Notification::make('send')
    ->title('Test Notifications')
    ->body('This is a test notification')
    ->icon('heroicon-o-bell')
    ->color('success')
    ->actions([
        \Filament\Notifications\Actions\Action::make('view')
            ->label('View')
            ->url('https://google.com')
            ->markAsRead()
    ])
    ->sendToFCM(auth()->user())
```
