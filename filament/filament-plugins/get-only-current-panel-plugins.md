# 🏂 Get Only Current Panel Plugins

on any plugin, you can create a Page/Resource/Widget for the selected panel, so if you need to show only the current panel Page/Resources/Widgets you can use this code in your PanelProvider

```php
->plugin(\TomatoPHP\FilamentPlugins\FilamentPluginsPlugin::make()->discoverCurrentPanelOnly())
```

\
