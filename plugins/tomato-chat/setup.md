# 🏗 Setup

to make this plugin work you need to inject the components on your app.js file and allow Echo to work so let's start by setting up some npm packages

```bash
yarn add laravel-echo agora-rtc-sdk-ng pusher-js autosize nprogress jquery
```

After installation you need to allow jquery on bootstrap.js file

```javascript
import $ from "jquery";
window.$ = $;
```

now make sure that you allow pusher connection with Echo

```javascript
import Echo from 'laravel-echo';

import Pusher from 'pusher-js';
window.Pusher = Pusher;

window.Echo = new Echo({
    broadcaster: 'pusher',
    key: import.meta.env.VITE_PUSHER_APP_KEY,
    cluster: import.meta.env.VITE_PUSHER_APP_CLUSTER,
    wsHost: import.meta.env.VITE_PUSHER_HOST ? import.meta.env.VITE_PUSHER_HOST : `ws-${import.meta.env.VITE_PUSHER_APP_CLUSTER}.pusher.com`,
    wsPort: import.meta.env.VITE_PUSHER_PORT ?? 80,
    wssPort: import.meta.env.VITE_PUSHER_PORT ?? 443,
    forceTLS: (import.meta.env.VITE_PUSHER_SCHEME ?? 'https') === 'https',
    enabledTransports: ['ws', 'wss'],
});
```

on your .env file please update the pusher details

now on your app.js allow the components

```javascript
import Chat from '../../vendor/tomatophp/tomato-chat/resources/js/components/Chat.vue';
import Video from '../../vendor/tomatophp/tomato-chat/resources/js/components/Video.vue';
import Call from '../../vendor/tomatophp/tomato-chat/resources/js/components/Call.vue';

createApp({
    render: renderSpladeApp({ el })
})
    .use(SpladePlugin, {
        max_keep_alive: 10,
        transform_anchors: false,
        progress_bar: true,
    })
    ....
    .component("Chat", Chat)
    .component("Video", Video)
    .component("Call", Call)
    .mount(el);
```

now it's the final step you need to import the style.css on your app.css file

```css
@import "../../vendor/tomatophp/tomato-chat/resources/css/style.css";
```

now run your build

```bash
yarn build
```

