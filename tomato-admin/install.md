# 🧠 Install

<figure><img src="../.gitbook/assets/screenshot (27).png" alt=""><figcaption></figcaption></figure>



{% embed url="https://www.youtube.com/watch?v=MdJPtoFn2xc" %}

to install this package you use this command

```
composer require tomatophp/tomato-admin
```

### Use Install Command

you can use the install command to build your admin panel

**NOTE**

before installing if you are not using `MacOS` please change the `Yarn` path of config on the [console-helper](../helpers/laravel-console-helpers.md) package after publishing the config file

```
php artisan tomato-admin:install
```

After Tomato installs everything run your npm

```
yarn
yarn build
```

### Allow Spatie Media Library inside your app

if you want to use media features inside your app you need to complete setup of Spatie Media Library, it's easy just publish the migration and migrate it.

```bash
php artisan vendor:publish --provider="Spatie\MediaLibrary\MediaLibraryServiceProvider"
```

now run your migration

```bash
php artisan migrate
```

now it's time to allow modules on your app by just adding this line to composer.json

```json
"autoload": {
    "psr-4": {
        ...
        "Modules\\" : "Modules/"
    }
},
```

