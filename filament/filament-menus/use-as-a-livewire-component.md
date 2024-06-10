# ⏯️ Use as a Livewire Component

go to route `admin/menus` and create a new menu and you will get the code of the livewire component

you can build a menu just by using this command as a livewire component

```html
<x-filament-menu menu="header" />
```

where `header` is a key to menu and you will get the code ready on the Table list of menus

you can use custom view ex:

```html
<x-filament-menu menu="header" view="menu-item" />
```

by default, we use Tailwind as a main view with this code

```html
@foreach ($menuItems as $item)
<a class="text-gray-500" href="{{ $item['url'] }}" @if($item['blank']) target="_blank" @endif>
    <span class="flex justify-between">
        @if(isset($item['icon']) && !empty($item['icon']))
        <x-icon class="w-4 h-4 mx-2" name="{{ $item['icon'] }}"></x-icon>
        @endif
        {{ $item['title'] }}
    </span>
</a>
@endforeach
```

or you can use a direct helper `menu($key)` to get the menu items

```html
@foreach (menu('header') as $item)
<a class="text-gray-500" href="{{ $item['url'] }}" @if($item['blank']) target="_blank" @endif>
    <span class="flex justify-between">
        @if(isset($item['icon']) && !empty($item['icon']))
        <x-icon class="w-4 h-4 mx-2" name="{{ $item['icon'] }}"></x-icon>
        @endif
        {{ $item['title'] }}
    </span>
</a>
@endforeach
```

