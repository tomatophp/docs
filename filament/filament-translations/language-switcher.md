# 🇪🇬 Use Language Switcher

You can use the language switcher in your panel by using the following plugin:

```php
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make())
```

**NOTE** your auth user table must have `lang` filed on the table to make this switch work fine.
