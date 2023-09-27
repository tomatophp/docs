# 🏗 Notification Service


to create a new template you can use template CRUD and make sure that the template key is unique because you will use it on every single notification.

### Send Notification

to send a notification you must use our helper SendNotification::class like

```php
SendNotification::make($template->providers)
    ->template($template->key)
    ->findTitle($matchesTitle)
    ->replaceTitle($titleFill)
    ->findBody($matchesBody)
    ->replaceBody($titleBody)
    ->model(User::class)
    ->id(User::first()->id)
    ->privacy('private')
    ->fire();
```

where `$template` is selected of the template by key and $matchesTitle and $matchesBody is an array of matches to replace the template and $titleFill and $titleBody are an array of values to replace the matches
