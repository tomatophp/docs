# 🔽 Dropdown

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-49-33.png" alt=""><figcaption></figcaption></figure>

you can use this component to create a dropdown like this

```markup
<x-tomato-admin-dropdown icon="bx bx-cog" class="bg-primary-600 hover:bg-primary-500 text-white rounded-full flex flex-col items-center justify-center p-2">
        <x-tomato-admin-dropdown-item
            type="link"
            :href="route('admin.products.toggle', $item->id) . '?action=is_activated'"
            :label="$item->is_activated ? __('Hide Product') : __('Show Product')"
            :success="!$item->is_activated"
            :danger="$item->is_activated"
            :icon="$item->is_activated ? 'bx bx-hide' : 'bx bx-show'"
        />
        <x-tomato-admin-dropdown-item
            black
            modal
            type="link"
            :href="route('admin.products.edit', $item->id)"
            :label="__('Edit Product')"
            icon="bx bx-edit"
        />
</x-tomato-admin-dropdown>
```
