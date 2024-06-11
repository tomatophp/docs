# 🔗 Discord Integration

to use the discord driver you must set the discord webhook on the settings hub and use the plugin method `useDiscord` like

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make()
    ->useDiscord()
)
```

now on your `.env` file add a `DISCORD_WEBHOOK` key with the webhook URL
