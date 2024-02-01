# 💿 Config

### Configuration

All options are described in `config/tomato-user-activities.php`.

### Using request hash in a standard log

If you would like to have a request identifier in your standard log, to match log events with requests you could add it to `config/logging.php`

```
'tap' => [TomatoPHP\TomatoUserActivities\LogCustomizers\HashLogCustomizer::class],
```

to `daily` channel. The resulting code should look like

```
    'channels' => [
        ...

        'daily' => [
            'driver' => 'daily',
            'path' => storage_path('logs/laravel.log'),
            'level' => 'debug',
            'days' => 14,
            'tap' => [TomatoPHP\TomatoUserActivities\LogCustomizers\HashLogCustomizer::class],
        ],

        ...
    ],
```

This log modifier can be used also in other channels, however, it uses extended `LineFormatter`.
