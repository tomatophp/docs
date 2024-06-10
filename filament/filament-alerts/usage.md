# ⏯️ Usage

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
