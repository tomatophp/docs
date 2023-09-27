# 🌉 Widget

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

as we get the Widget Facade service to register the widgets to the dashboard homepage, we get this component to register the same widgets anywhere.

### Use

you can use it like this

```html
<x-tomato-admin-widget
    :counter="300"
    :title="__('Projects')"
    icon="bx bx-category"
/>
```

or you can just pass a direct model and we will count it

```html
<x-tomato-admin-widget
    model="User::class"
    :title="__('Projects')"
    icon="bx bx-category"
/>
```

and you can change the query like this

```html
<x-tomato-admin-widget
    model="User::class"
    :query="[
        'is_activated' => true
    ]"
    :title="__('Projects')"
    icon="bx bx-category"
/>
```
