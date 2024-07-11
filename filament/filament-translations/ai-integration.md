# 🤖 AI Integration

### ChatGPT Integration

If you want to use ChatGPT to auto-translate your languages, you need to install `OpenAI` package by running:

```bash
composer require openai-php/laravel
```

now you need to add the following to your `.env` file:

```dot
OPENAI_API_KEY=
OPENAI_ORGANIZATION=
```

allow the feature on your panel provider by adding the following:

```php
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make()->allowGPTScan())
```

### Google Translate Integration

If you want to use Google Translate for auto-translating your languages, you need to install the `stichoza/google-translate` package by running:

```bash
composer require stichoza/google-translate-php
```

Enable the feature on your admin panel provider file by adding the following:

```php
$panel->plugin(\TomatoPHP\FilamentTranslations\FilamentTranslationsPlugin::make()->allowGoogleTranslateScan())
```
