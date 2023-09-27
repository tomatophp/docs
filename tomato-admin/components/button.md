# Button

we are using buttons everywhere on the dashboard so we do 1 component to manage buttons types and button multi style 

## Use

you can add a new button like this

```html
<x-tomato-admin-button 
    :modal="true" 
    :href="route('admin.community-events.create')" 
    type="link"
>
    {{ __('Create User') }}
</x-tomato-admin-button>
```

or you can use it as a icon button inside table like this

```html
<x-tomato-admin-button 
    success 
    type="icon" 
    label="{{trans('tomato-admin::global.crud.view')}}" 
    modal 
    :href="route('admin.users.show', $item->id)"
>
    <x-heroicon-s-eye class="h-6 w-6"/>
</x-tomato-admin-button>
```

and the button working as well as the `x-splade-link` so you can create a delete button like this

```html
<x-tomato-admin-button 
    danger 
    type="icon" 
    label="{{trans('tomato-admin::global.crud.delete')}}" 
    :href="route('admin.bills.destroy', $item->id)"
    confirm="{{trans('tomato-admin::global.crud.delete-confirm')}}"
    confirm-text="{{trans('tomato-admin::global.crud.delete-confirm-text')}}"
    confirm-button="{{trans('tomato-admin::global.crud.delete-confirm-button')}}"
    cancel-button="{{trans('tomato-admin::global.crud.delete-confirm-cancel-button')}}"
    method="delete"
>
    <x-heroicon-s-trash class="h-6 w-6"/>
</x-tomato-admin-button>
```