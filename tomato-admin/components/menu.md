# 📖 Menu

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

as you know on the config page you can use a custom menu view for the sidebar of the dashboard so we build a component to make it easy to add a new menu with groups to this custom view

### Use

you can use it like this

```html
<x-menu-group 
    key="users" 
    label="{{__('ALC')}}"
>
    <x-menu-item 
        url="{{ route('admin.users.index') }}" 
        icon="bx bxs-user"
        badge="10"
    >
        {{__('Users')}}
    </x-menu-item>
    <x-menu-item 
        url="{{ route('admin.roles.index') }}" 
        icon="bx bx-lock" 
    >
        {{__('Roles')}}
    </x-menu-item>
</x-menu-group>
```

the group component used to group items together, but you can use menu items direct without a group
