# 🧠 Install

<figure><img src="../.gitbook/assets/screenshot (27).png" alt=""><figcaption></figcaption></figure>

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
