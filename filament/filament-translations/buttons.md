# 🔘 Buttons

### Show or hide buttons in the UI

You can show or hide the buttons in the UI by changing the config file. By default, all buttons are shown.

```php
'show_import_button' => true,
'show_export_button' => false,
'show_scan_button' => false ,
```

### Allow Clear All Translations Button

If you want to allow the user to clear all translations, you need to add the following to your panel provider:

```php
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make()->allowClearTranslations())
```

### Allow Create Button

If you want to allow the user to create a new language, you need to add the following to your panel provider:

```php
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make()->allowCreate())
```

