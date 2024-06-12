# 🏗️ Installation

```
composer require tomatophp/filament-fcm
```

after installing your package you need to update these keys in your `.env` file

```
# Firebase Project
FIREBASE_API_KEY=
FIREBASE_AUTH_DOMAIN=
FIREBASE_DATABASE_URL=
FIREBASE_PROJECT_ID=
FIREBASE_STORAGE_BUCKET=
FIREBASE_MESSAGING_SENDER_ID=
FIREBASE_APP_ID=
FIREBASE_MEASUREMENT_ID=

# Firebase Cloud Messaging
FIREBASE_VAPID=

# Firebase Alert Sound
FCM_ALERT_SOUND=
```

after updating the clear config

```bash
php artisan config:clear
```

then please run this command

```bash
php artisan filament-fcm:install
```

if you are not using this package as a plugin please register the plugin on `/app/Providers/Filament/AdminPanelProvider.php`

```php
->plugin(\TomatoPHP\FilamentFcm\FilamentFcmPlugin::make())
```
