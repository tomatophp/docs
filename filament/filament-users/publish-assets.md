# 📢 Publish Assets

### Publish Assets <a href="#user-content-publish-assets" id="user-content-publish-assets"></a>

you can publish a config file by using this command

```
php artisan vendor:publish --tag="filament-users-config"
```

you can publish language files by use this command

```
php artisan vendor:publish --tag="filament-users-lang"
```

### Publish Resource <a href="#user-content-publish-resource" id="user-content-publish-resource"></a>

you can publish the resource to your project

```
php artisan filament-user:publish
```

it will publish the resource to your project

than go to `filament-user.php` config file and change the `publish_resource` to `true`
