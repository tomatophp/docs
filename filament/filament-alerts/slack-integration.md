# 🔗 Slack Integration

to use slack driver you must set the slack webhook on the settings hub and use the plugin method `useSlack` like

```php
->plugin(\TomatoPHP\FilamentAlerts\FilamentAlertsPlugin::make()
    ->useSlack()
)
```

now on your `.env` file add a `SLACK_WEBHOOK` key with the webhook URL
