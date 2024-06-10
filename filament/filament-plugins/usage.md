# ⏯️ Usage

you can create a new plugin using just a command

```bash
php artisan filament-plugins:generate
```

or you can use the GUI to create a new plugin, after creating a plugin you need to make sure that it's loaded on the composer by running this command

```bash
composer dump-autoload
```

after creating the plugin you can create a new table inside it and then run the migration generator to convert it to a migration file then you can use the GUI to generate resources, pages, widgets or model, or you can easily use this commands

```bash
php artisan filament-plugins:model
php artisan filament-plugins:resource
php artisan filament-plugins:page
php artisan filament-plugins:widget
```

it will generate the files for you and you can use it directly, please note that you need to generate the model first then use other commands
