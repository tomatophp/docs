---
description: Chat Plugin to build full Audio/Video realtime chat app
---

# ⚔ Tomato Chat

<figure><img src="../../.gitbook/assets/screenshot (25).png" alt=""><figcaption></figcaption></figure>

our plugin is built in a fork of [Chatify Laravel Package](https://github.com/munafio/chatify) with a lot of options and integration with agora SDK and UI for audio/video calls.

### Installation

```
composer require tomatophp/tomato-chat
```

after installing your package please run this command

```
php artisan tomato-chat:install
```

### Publish Assets

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-chat-config"
```

you can publish views file by using this command

```
php artisan vendor:publish --tag="tomato-chat-views"
```

you can publish languages file by using this command

```
php artisan vendor:publish --tag="tomato-chat-lang"
```

you can publish migrations file by using this command

```
php artisan vendor:publish --tag="tomato-chat-migrations"
```

### Accept Global Notification On Call

you can make your app subscribe to a pusher event or call anywhere by binding the event on `app.js`&#x20;

```javascript
const Splade = inject("$splade");

const pusher = new Pusher(import.meta.env.VITE_PUSHER_APP_KEY, {
    cluster: import.meta.env.VITE_PUSHER_APP_CLUSTER,
    key: import.meta.env.VITE_PUSHER_APP_KEY,
    wsHost: import.meta.env.VITE_PUSHER_HOST ? import.meta.env.VITE_PUSHER_HOST : `ws-${import.meta.env.VITE_PUSHER_APP_CLUSTER}.pusher.com`,
    wsPort: import.meta.env.VITE_PUSHER_PORT ?? 80,
    wssPort: import.meta.env.VITE_PUSHER_PORT ?? 443,
    forceTLS: (import.meta.env.VITE_PUSHER_SCHEME ?? 'https') === 'https',
    enabledTransports: ['ws', 'wss'],
    authEndpoint: $('meta[name="pusher-auth"]').attr('content'),
    auth: {
        headers: {
            'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
        }
    }
});

const channelName = "private-chatify";
const channel = pusher.subscribe(`${channelName}.${$('meta[name="auth_id"]').attr('content')}`);

channel.bind("video-call", function (data) {
    Splade.visit(data.url);
});

channel.bind("audio-call", function (data) {
    Splade.visit(data.url);
});
```

and on HTML add this `<head>`

```html
<meta name="pusher-auth" content="{{ route(config('tomato-chat.routes.name')."pusher.auth") }}">
<meta name="auth_id" content="{{ auth()->user()?->id }}">
```

### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-chat/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-chat/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-chat/blob/master/LICENSE.md) for more information.
