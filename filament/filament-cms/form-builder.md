# 🔡 Form Builder

### Add Form Field Type

you can add more fields to the form builder by using this method on your provider.

```php
use TomatoPHP\FilamentCms\Services\FilamentCMSFormFields;
use TomatoPHP\FilamentCms\Services\Contracts\CmsFormFieldType;

FilamentCMSFormFields::register([
    CmsFormFieldType::make('code')
        ->className(CodeEditor::class)
        ->color('warning')
        ->icon('heroicon-s-code-bracket-square')
        ->label('Code Editor'),
]);
```

### Use Your Form Builder

after creating your form you can use it by `key` like this

```php
use TomatoPHP\FilamentCms\Services\FilamentCMSFormBuilder;

FilamentCMSFormBuilder::make('xvssd')->build()
```

### Use Form Requests to Submit your form data

you can use form requests to submit your form data by using this method on your provider.

```php
use TomatoPHP\FilamentCms\Services\FilamentCMSFormBuilder;

FilamentCMSFormBuilder::make('xvssd')->send($data)
```
