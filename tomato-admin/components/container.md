# Container

we build a container component to make it easy to merge between page and model view, so this container convert any page to work as a page and model on the same time.

### Use

you can use it like

```html
<x-tomato-admin-container 
    label="{{__('Create User')}}"
>
    <!-- Your Content Here -->
</x-tomato-admin-container>
```

you can access this page as a direct page or using `modal` on the `x-splade-link` or `x-tomato-admin-button` like this

```html
<x-tomato-admin-button 
    modal
    :href="route('admin.users.create')"
>
    {{ __('Create User') }}
</x-tomato-admin-button>
```
### Slots

this container has 2 slots you can use it to custom your view

```html
<x-slot:buttons>
    <!-- Your Buttons Here -->
</x-slot:buttons>
```

this slot use to attach more buttons on the top left side of the page

```html
<x-slot:body>
    <!-- Your Content Here -->
</x-slot:body>
```

this slot use to add content after the card.