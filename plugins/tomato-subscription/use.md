# 📐 Use

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

#### Use the Subscription trait on your model

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
