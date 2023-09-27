---
description: >-
  Plan subscription with selected features to build a feature control plan for
  Tomato
---

# 💳 Tomato Subscription

<figure><img src="../../.gitbook/assets/screenshot (10).png" alt=""><figcaption></figcaption></figure>

### Installation

```
composer require tomatophp/tomato-subscription
```

after you install run this command

```
php artisan tomato-subscription:install
```

### Using

you can generate a new feature by using this command

```
php artisan tomato-feature:generate
```

it will generate a feature for you and you can add it to your plan.

to make some routes guard by our plan feature control:

#### Add Model to config

go to `config/tomato-subscription.php` and add new models like

```
[
    "label" => "Users",
    "id" => \App\Models\User::class
],
```

#### Use Subscription trait on your model

you need to add this trait to your model

```
use TomatoPHP\TomatoSubscription\Traits\HasPlanSubscription;

class User extends Authenticatable
{
    use HasPlanSubscription;
    ...
```

#### Add Middleware to your routes

you can add the middleware to your routes like

```
\TomatoPHP\TomatoSubscription\Http\Middleware\UserHasBeenSubscribedToPlan::class
```

now, your app is ready to use our package.



### Changelog

Please see [CHANGELOG](https://github.com/tomatophp/tomato-subscription/blob/master/CHANGELOG.md) for more information on what has changed recently.

### Security

Please see [SECURITY](https://github.com/tomatophp/tomato-subscription/blob/master/SECURITY.md) for more information about the security.

### Credits

* [Fady Mondy](https://www.github.com/3x1io)

### License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/tomato-subscription/blob/master/LICENSE.md) for more information.
