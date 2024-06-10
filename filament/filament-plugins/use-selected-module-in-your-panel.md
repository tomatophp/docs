# 📶 Use Selected Module in your panel

you can use the selected module in your panel by using this code in your PanelProvider

```php
->plugin(\TomatoPHP\FilamentPlugins\FilamentPluginsPlugin::make()->modules([
    'CRM'
]))
```

so you will see only the selected modules in your panel
