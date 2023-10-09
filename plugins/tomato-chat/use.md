# 📐 Use

### Accept Global Notification On Call

you can make your app subscribe to a pusher event or call anywhere by binding the event on `app.js`&#x20;

```javascript
import {inject} from "vue";

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
