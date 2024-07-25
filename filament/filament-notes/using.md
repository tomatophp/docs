# ⏯️ Using

you can use it as a resource or you can use it as a widget by just registering a widget on your panel provider like this

```php
$panel->widgets([
    \TomatoPHP\FilamentNotes\Filament\Widgets\NotesWidget::class
])
```

### Use Livewire Component

you can use selected notes anywhere using the livewire component

```html
<livewire:note-action :note="$note" />
```

### Use Groups & Status

to use this feature you need to install [filament-types](https://www.github.com/tomatophp/filament-types) or use this command

```bash
composer require tomatophp/filament-types
```

then you can use this feature by adding this method to the plugin

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make()
    ->useStatus()
    ->useGroups()
)
```

### Use Convert Note To Notification

to use this feature you need to install [filament-alerts](https://www.github.com/tomatophp/filament-alerts) or use this command

```bash
composer require tomatophp/filament-alerts
```

then you can use this feature by adding this method to the plugin

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make()
    ->useNotification()
)
```

### Use Share Note With Public Link

you can generate a public link and share it with others by allowing this feature on your provider

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make()
    ->useShareLink()
)
```

### Use User Access Permissions

you can use this feature to allow only selected users to access the notes by allowing this feature on your provider

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make()
    ->useUserAccess()
)
```

### Use Checklist

you can use this feature to add a checklist to your notes by allowing this feature on your provider

```php
$panel->plugin(\TomatoPHP\FilamentNotes\FilamentNotesPlugin::make()
    ->useChecklist()
)
```
