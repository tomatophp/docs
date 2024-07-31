# 🎇 Folders API

now you can access your media and folders using API you have 2 endpoints

* `/api/folders` to get all folders
* `/api/folders/{id}` to get folder by id with sub folders and media files

to allow this feature you need to publish the config file by use this command

```bash
php artisan vendor:publish --tag="filament-media-manager-config"
```

then you can set `api.active` to `true` on the config file

```php
'api' => [
    "active" => true,
],
```
