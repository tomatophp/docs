# 👨‍💻 Command Line

### Scan Using Command Line

You can scan your project to get all the language tags and save them to the database

```bash
php artisan filament-translations:import
```

### Custom Import Command

You can create your own command to import the translations, and add your custom import class to the config file like this:

```php
'path_to_custom_import_command' => ImportTranslations::class,
```

This command will automatically run when you click on the "Scan For New Languages" button in the UI.

### Scan Path to JSON File

you can scan the selected path and generate a language for it by just using this command

```bash
php artisan filament-translations:scan
```
