# 📺 Youtube Integration

you can allow import content from YouTube by adding `YOUTUBE_KEY` to your `.env`

```dot
YOUTUBE_KEY=YOUR_YOUTUBE_KEY
```

now on your panel provider `/app/Providers/Filament/AdminPanelProvider.php` add this method

```php
->plugin(\TomatoPHP\FilamentCms\FilamentCMSPlugin::make()->allowYoutubeImport())
```
