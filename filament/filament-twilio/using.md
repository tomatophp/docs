# ⏯️ Using

first of all, you need to add this variable to your `.env` file

```
TWILIO_SID=
TWILIO_TOKEN=
TWILIO_SENDER_NUMBER=
```

then clear you cache

```bash
php artisan config:cache
```

now on your User model add this trait

```php
use TomatoPHP\FilamentTwilio\Traits\InteractsWithTwilioWhatsapp;

class User extends Authenticatable
{
    use InteractsWithTwilioWhatsapp;
}
```

now you are ready to use the notification

```php
\Filament\Notifications\Notification::make()
    ->body('Your Message You Like To Send Here!')
    ->sendToTwilioWhatsapp($user);
```

or you can use it from the user model direct

```php
$user->notifyTwilioWhatsapp('Your Message You Like To Send Here!');
```
