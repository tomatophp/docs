# 🧠 Install

you need to install vue-flow to make this package work.

```bash
yarn add @vue-flow/background @vue-flow/core @vue-flow/controls @vue-flow/minimap @vue-flow/node-toolbar @vue-flow/node-resizer 
```

Now you need to build your assets

```bash
yarn build
```

add this line to your app.js

```javascript
import TomatoDiagram from "../../vendor/tomatophp/tomato-builder/resources/js/components/TomatoDiagram.vue";


createApp({
    render: renderSpladeApp({ el })
})
    .use(SpladePlugin, {
        max_keep_alive: 10,
        transform_anchors: false,
        progress_bar: true,
    })
    .component("TomatoDiagram", TomatoDiagram)
    ...
    .mount(el);
```
