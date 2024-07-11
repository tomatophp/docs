# 🌠 Import & Export

#### Custom Import Command

You can create your own command to import the translations, and add your custom import class to the config file like this:

```php
'path_to_custom_import_command' => ImportTranslations::class,
```

This command will automatically run when you click on the "Scan For New Languages" button in the UI.

#### Custom Excel Import

You can create your own Excel import to import the translations, and add your custom import class to the config file like this:

```php
'path_to_custom_excel_import' => CustomTranslationImport::class,
```

The import class is based on the Laravel Excel package. You can check the documentation [here](https://docs.laravel-excel.com/3.1/imports/). This import will automatically run when you click on the "Import" button in the UI.

#### Custom Excel Export

You can create your own Excel export to export the translations in your own format, and add your custom export class to the config file like this:

```php
'path_to_custom_excel_export' => CustomTranslationExport::class,
```

The export class is based on the Laravel Excel package. You can check the documentation [here](https://docs.laravel-excel.com/3.1/imports/). This import will automatically run when you click on the "Export" button in the UI.
