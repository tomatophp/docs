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
    ->sendToDiscord(auth()->user())
    ->sendToEmail(auth()->user())
    ->broadcast(auth()->user())
    ->sendToDatabase(auth()->user())
    ->sendToSlack(auth()->user())
    ->sendToFCM(auth()->user())
```

### Notification Service

to create a new template you can use template CRUD and make sure that the template key is unique because you will use it on every single notification.

to send a notification you must use our helper SendNotification::class like

```php
SendNotification::make($template->providers)
    ->template($template->key)
    ->findTitle($matchesTitle)
    ->replaceTitle($titleFill)
    ->findBody($matchesBody)
    ->replaceBody($titleBody)
    ->model(User::class)
    ->id(User::first()->id)
    ->privacy('private')
    ->fire();
```

where `$template` is selected of the template by key and $matchesTitle and $matchesBody is an array of matches to replace the template and $titleFill and $titleBody are an array of values to replace the matches

#### Notification Channels

you can use multiple notification channels like

* Email
* SMS
* FCM
* Pusher
* Database
* Slack
* Discord

it can be working with direct user methods like

```php
$user->notifySMSMisr(string $message);
$user->notifyEmail(string $message, ?string $subject = null, ?string $url = null);
$user->notifyFCMSDK(string $message, string $type='web', ?string $title=null, ?string $url=null, ?string $image=null, ?string $icon=null, ?array $data=[]);
$user->notifyPusherSDK(string $token, string $title, string $message);
$user->notifyDB(string $message, ?string $title=null, ?string $url =null);
$user->notifySlack(string $title,string $message=null,?string $url=null, ?string $image=null, ?string $webhook=null);
$user->notifyDiscord(string $title,string $message=null,?string $url=null, ?string $image=null, ?string $webhook=null);
```
