# 🦘 Slots

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-58-59.png" alt=""><figcaption></figcaption></figure>

The Splade table is a magical component inside the Splade system, but we need some extra slots inside.

## Actions Slot

we add a new slot inside the table to add more actions to the actions button, like import, export or more links to other tables or direct filters

you can use it like this

```html
<x-slot:actions>
    <x-tomato-admin-table-action secondary href="{{route('admin.types.accounts.type.index')}}" label="{{__('Accounts Types')}}" icon="bx bx-category" />
</x-slot:actions>
```

## Header Slot

sometimes you need to add a widget inside the table to change their data when the filter or pagination changes inside the table you can do that by using the header slot

you can use it like this

```markup
<x-slot:header>
    @if(config('tomato-crm.features.groups'))
        <div class="grid grid-cols-1 lg:grid-cols-4 gap-4 mb-3">
            @foreach($groups as $group)
                <div class="relative border border-gray-200 dark:bg-gray-800 dark:border-gray-700 p-4 rounded-lg bg-white @if(isset(request()->get('filter')['group_id']) && request()->get('filter')['group_id'] == $group->id) ring-2 ring-primary-500 @endif">
                    <x-splade-link :href="route('admin.groups.edit', $group->id)" modal class="absolute top-3 rtl:right-3 ltr:left-3 text-warning-500">
                        <i class="bx bx-edit"></i>
                    </x-splade-link>

                    <div @click.prevent="table.updateQuery('filter[group_id]', @js($group->id))" class="flex flex-col items-center justify-center cursor-pointer">
                        <i class="{{$group->icon}} bx-lg" style="color: {{$group->color}}"></i>
                        <h1 class="font-bold text-2xl">{{$group->name}}</h1>
                        <h1 class="text-gray-400 text-sm">{{$group->accounts()->count()}} {{__('Customer')}}</h1>
                    </div>
                </div>
            @endforeach
            <x-splade-link modal :href="route('admin.groups.create')" class="border border-gray-200 dark:border-gray-700 px-4 py-8 rounded-lg bg-primary-500 text-white flex flex-col items-center justify-center">
                <i class="bx bx-plus-circle bx-lg"></i>
                <h1 class="font-bold text-xl">{{__('Create New Group')}}</h1>
            </x-splade-link>
        </div>
    @endif
</x-slot:header>
```
