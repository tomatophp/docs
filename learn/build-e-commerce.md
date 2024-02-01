# 🛍 Build E-Commerce

hi, community.

Introducing #tomatophp, a cutting-edge open-source Laravel package designed to streamline development within the VILT stack environment. This innovative ecosystem leverages the power of Splade to effortlessly generate modern, high-performance single-page applications (SPAs) using only Blade files. #tomatophp redefines the development experience, making it both efficient and enjoyable.

As we progress, we continuously enhance our ecosystem by incorporating additional features into our plugins. Presently, we have developed a comprehensive e-commerce system using these plugins. In this article, we will guide you through the implementation process, demonstrating how you can seamlessly integrate a robust e-commerce system into your application.

### Install Tomato Admin

you need to install tomato-admin plugin on your fresh Laravel app so let's create a new Laravel app.

```bash
composer create-project laravel/laravel tomato
```

> if you don't have an environment for Laravel you can use this [doc](https://docs.tomatophp.com/get-started/environment-setup) to build one on your Ubuntu Linux.

now cd inside your project folder change .env of your database and make sure that your Laravel app is running and the database is connected, you can check that by running migrations

```bash
php artisan migrate
```

now let's start installing tomato-admin

```bash
composer require tomatophp/tomato-admin
```

after the composer is done run this command for auto-install

```bash
php artisan tomato-admin:install
```

if you are using macOS you can easily use auto yarn package install if not just build your assets like this

```bash
yarn & yarn build
```

now you have tomato-admin installed on your Laravel project.

we will use some media on our package to we need to publish Spatie Media Library migrations

```bash
php artisan vendor:publish --provider="Spatie\MediaLibrary\MediaLibraryServiceProvider" --tag="medialibrary-migrations"
```

if this command does not work please use this command

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5h8jkfafatf1nqtuh8ib.png)

```bash
php artisan vendor:publish
```

then on the search type `media` and select the migration one.

now migrate your files

```bash
php artisan migrate
```

you can check your browser now and you will see a homepage like this

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wrm0574dwbhwx43nvxgk.png)

we need to change `HOME` const on the `RouteServiceProvider.php` to be `/admin` to make the redirect after auth to admin.

### Install Tomato Roles

No e-commerce system is complete without a robust role management structure. To fulfill this essential requirement, we'll be installing 'tomato-roles' to seamlessly handle roles within our mission to build a comprehensive e-commerce system.

```bash
composer require tomatophp/tomato-roles
```

after the composer is done run this command

```bash
php artisan tomato-roles:install
```

now go to your `app\Models\User.php` and add this trait to it

```php
use \Spatie\Permission\Traits\HasRoles;
```

now your dashboard is ready to log in using `admin@admin.com` and `password` as a password from this URL `/admin/login`

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3qg11z9vp04z3vc75pgg.png)

> if you try to access any page you will be redirected to `Two-factor Confirmation` If you don't go it for now, you can easily stop it by removing `implements MustVerifyEmail` from your `User.php` model.

### Install Tomato CRM

As an integral part of our e-commerce system, the management of customer interactions, authentications, and other crucial actions is paramount. To efficiently handle these aspects, we'll be installing 'tomato-crm.' Let's proceed with the installation to empower our system with advanced customer relationship management capabilities.

```bash
composer require tomatophp/tomato-crm
```

now let's install it

```bash
php artisan tomato-crm:install
```

let's publish `Accounts.php` model to our app to custom it

```bash
php artisan vendor:publish --tag="tomato-crm-model"
```

and you need to publish tomato-crm config

```bash
php artisan vendor:publish --tag="tomato-crm-config"
```

on `tomato-crm.php` config change the model path to like this

```php
"model" => \App\Models\Account::class,
```

now we need to add a new guard to our app, so let's add it on the config `auth.php` like this.

```php
<?php

return [

    /*
    |--------------------------------------------------------------------------
    | Authentication Defaults
    |--------------------------------------------------------------------------
    |
    | This option controls the default authentication "guard" and password
    | reset options for your application. You may change these defaults
    | as required, but they're a perfect start for most applications.
    |
    */

    'defaults' => [
        'guard' => 'web',
        'passwords' => 'users',
    ],

    /*
    |--------------------------------------------------------------------------
    | Authentication Guards
    |--------------------------------------------------------------------------
    |
    | Next, you may define every authentication guard for your application.
    | Of course, a great default configuration has been defined for you
    | here which uses session storage and the Eloquent user provider.
    |
    | All authentication drivers have a user provider. This defines how the
    | users are actually retrieved out of your database or other storage
    | mechanisms used by this application to persist your user's data.
    |
    | Supported: "session"
    |
    */

    'guards' => [
        'web' => [
            'driver' => 'session',
            'provider' => 'users',
        ],
        'accounts' => [
            'driver' => 'session',
            'provider' => 'accounts',
        ]
    ],

    /*
    |--------------------------------------------------------------------------
    | User Providers
    |--------------------------------------------------------------------------
    |
    | All authentication drivers have a user provider. This defines how the
    | users are actually retrieved out of your database or other storage
    | mechanisms used by this application to persist your user's data.
    |
    | If you have multiple user tables or models you may configure multiple
    | sources which represent each model / table. These sources may then
    | be assigned to any extra authentication guards you have defined.
    |
    | Supported: "database", "eloquent"
    |
    */

    'providers' => [
        'users' => [
            'driver' => 'eloquent',
            'model' => App\Models\User::class,
        ],
        'accounts' => [
            'driver' => 'eloquent',
            'model' => App\Models\Account::class,
        ],
    ],

    /*
    |--------------------------------------------------------------------------
    | Resetting Passwords
    |--------------------------------------------------------------------------
    |
    | You may specify multiple password reset configurations if you have more
    | than one user table or model in the application and you want to have
    | separate password reset settings based on the specific user types.
    |
    | The expiry time is the number of minutes that each reset token will be
    | considered valid. This security feature keeps tokens short-lived so
    | they have less time to be guessed. You may change this as needed.
    |
    | The throttle setting is the number of seconds a user must wait before
    | generating more password reset tokens. This prevents the user from
    | quickly generating a very large amount of password reset tokens.
    |
    */

    'passwords' => [
        'users' => [
            'provider' => 'users',
            'table' => 'password_reset_tokens',
            'expire' => 60,
            'throttle' => 60,
        ],
    ],

    /*
    |--------------------------------------------------------------------------
    | Password Confirmation Timeout
    |--------------------------------------------------------------------------
    |
    | Here you may define the amount of seconds before a password confirmation
    | times out and the user is prompted to re-enter their password via the
    | confirmation screen. By default, the timeout lasts for three hours.
    |
    */

    'password_timeout' => 10800,

];
```

now clear your config cache

```bash
php artisan config:clear
```

now rebuild your assets

```bash
yarn & yarn build
```

now your CRM is ready you can check it on your dashboard

### Install Tomato Wallet

For seamless transaction management between customers and vendors within the e-commerce system, a robust payment handler is crucial. Introducing 'tomato-wallet,' a feature-rich package that not only manages customer wallets but also seamlessly handles payments. Packed with a multitude of integrated payment gateways, 'tomato-wallet' ensures a magical experience in managing transactions. Let's proceed with the installation to unlock the full potential of this powerful payment solution.

```bash
composer require tomatophp/tomato-wallet
```

let's install it

```bash
php artisan tomato-wallet:install
```

now we need to implement `Wallet` interface to our `Account.php` and add `HasWallet` trait to it to make the wallet of the customer work, your Account model must be like this

```php
<?php

namespace App\Models;

use Bavix\Wallet\Interfaces\Wallet;
use Bavix\Wallet\Traits\HasWallet;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;
use Illuminate\Foundation\Auth\User as Authenticatable;
use Illuminate\Notifications\Notifiable;
use Laravel\Sanctum\HasApiTokens;
use Spatie\Macroable\Macroable;
use Spatie\MediaLibrary\HasMedia;
use Spatie\MediaLibrary\InteractsWithMedia;
use Spatie\Permission\Traits\HasRoles;
use TomatoPHP\TomatoCrm\Models\Group;

/**
 * @property integer $id
 * @property string $name
 * @property string $username
 * @property string $loginBy
 * @property string $address
 * @property string $type
 * @property string $password
 * @property string $otp_code
 * @property string $otp_activated_at
 * @property string $last_login
 * @property string $agent
 * @property string $host
 * @property integer $attempts
 * @property boolean $login
 * @property boolean $activated
 * @property boolean $blocked
 * @property string $deleted_at
 * @property string $created_at
 * @property string $updated_at
 * @property AccountsMeta[] $accountsMetas
 * @property Activity[] $activities
 * @property Comment[] $comments
 * @property Model meta($key, $value)
 * @property Location[] $locations
 */
class Account extends Authenticatable implements HasMedia, Wallet
{
    use InteractsWithMedia;
    use HasApiTokens, HasFactory, Notifiable;
    use HasWallet;

    /**
     * @var array
     */
    protected $fillable = [
        'email',
        'phone',
        'parent_id',
        'type',
        'name',
        'username',
        'loginBy',
        'address',
        'password',
        'otp_code',
        'otp_activated_at',
        'last_login',
        'agent',
        'host',
        'is_login',
        'is_active',
        'deleted_at',
        'created_at',
        'updated_at'
    ];

    protected $casts = [
        'is_login' => 'boolean',
        'is_active' => 'boolean'
    ];
    protected $dates = [
        'deleted_at',
        'created_at',
        'updated_at',
        'otp_activated_at',
        'last_login',
    ];


    protected $appends = [
        'birthday',
        'gender',
        'more'
    ];

    public function getMoreAttribute()
    {
        $metas = $this->accountsMetas()->get()->pluck('value', 'key')->toArray();
        return $metas;
    }

    public function getBirthdayAttribute()
    {
        return $this->meta('birthday') ?: null;
    }

    public function getGenderAttribute()
    {
        return $this->meta('gender') ?: null;
    }

    /**
     * @return \Illuminate\Database\Eloquent\Relations\HasMany
     */
    public function accountsMetas()
    {
        return $this->hasMany('TomatoPHP\TomatoCrm\Models\AccountsMeta');
    }

    /**
     * @param string $key
     * @param string|null $value
     * @return Model|string
     */
    public function meta(string $key, string|null $value=null): Model|string|null
    {
        if($value){
            return $this->accountsMetas()->updateOrCreate(['key' => $key], ['value' => $value]);
        }
        else {
            return $this->accountsMetas()->where('key', $key)->first()?->value;
        }
    }
    /**
     * @return \Illuminate\Database\Eloquent\Relations\HasMany
     */
    public function activities()
    {
        return $this->hasMany('TomatoPHP\TomatoCrm\Models\Activity');
    }

    /**
     * @return \Illuminate\Database\Eloquent\Relations\HasMany
     */
    public function comments()
    {
        return $this->hasMany('TomatoPHP\TomatoCrm\Models\Comment');
    }

    /**
     * @return \Illuminate\Database\Eloquent\Relations\HasMany
     */
    public function locations()
    {
        return $this->hasMany('TomatoPHP\TomatoCrm\Models\Location');
    }

    public function groups(){
        return $this->belongsToMany(Group::class, 'account_groups', 'account_id', 'group_id');
    }
}
```

now your wallet is working you can start any transaction and check the customer's balance.

### Install Tomato CMS

In any functioning e-commerce setup, a well-optimized front end is indispensable. To enhance SEO performance and add essential content such as posts and pages, we'll be incorporating our 'tomato-cms' package. Let's proceed with the installation to seamlessly integrate this package and elevate our e-commerce platform.

```bash
composer require tomatophp/tomato-cms
```

now let's install it

```bash
php artisan tomato-cms:install
```

### Install Tomato Themes

To craft a dynamic frontend tailored as a theme, we'll be utilizing the 'tomato-themes' package. This package simplifies the implementation of multi-themes for your project, employing a Hierarchical Model-View-Controller (HMVC) architecture. Let's initiate the installation process for 'tomato-themes' to facilitate the seamless integration of diverse themes into your project.

```bash
composer require tomatophp/tomato-themes
```

now let's install it

```bash
php artisan tomato-themes:install
```

now rebuild your assets

```bash
yarn & yarn build
```

make sure that you have `Themes` folder in your project root and add this line to your `composer.json`

```json
    "autoload": {
        "psr-4": {
            "App\\": "app/",
            "Database\\Factories\\": "database/factories/",
            "Database\\Seeders\\": "database/seeders/",
            "Themes\\": "Themes/"
        }
    },
```

now you need to reload the composer

```bash
composer dump-autoload
```

now inside your tailwind.config.js add these lines\


```json
content: [
    ...
    "./Themes/**/*.blade.php",
    "./Themes/**/**/*.blade.php",
],
```

now your theme is ready to upload or create a new theme.

### Install Tomato E-Commerce

Now that we have our foundational elements in place, including a ready CRM, role management, and several essential packages, it's time to bring it all together by installing the E-Commerce System. The seamless integration of these components promises a robust and feature-rich platform. Let's proceed with the installation to witness the culmination of our efforts in building a comprehensive and efficient E-Commerce System.

```bash
composer require tomatophp/tomato-ecommerce
```

let's install it

```bash
php artisan tomato-ecommerce:install
```

now everything i ready to install our e-commerce theme.

this package will install tomato-products, tomato-orders, tomato-offers, tomato-branches for you

to make everything work fine you need some actions, we need to install tomato-branches

```bash
php artisan tomato-branches:install
```

after that, you need to create just 1 `Shipping Vendor` from this endpoint `/admin/shipping-vendors`

now you need to change your site SEO data and your site Logo from this endpoint `/admin/settings/seo` upload your logos and change the Site Name.

### Install E-commerce Theme

Having established a solid foundation, including CRM, role management, and various essential packages, we're now ready to enhance the visual appeal of our E-Commerce and CMS platforms. Introducing our user-friendly theme with a simple yet stylish design – an ideal canvas for customization. Let's embark on the installation process to seamlessly integrate this theme and provide users the flexibility to tailor it to their preferences.

inside your Themes Folder clone this repo

```bash
cd Themes
```

now clone our Theme.

```bash
git clone git@github.com:tomatophp/Ecommerce.git
```

now go to your dashboard `/themes` and you will get the new theme you can just activate it.

> Please note that you must not have `/` route on your main `routes/web.php` because these routes can override the Theme Routes.

to fix style rebuild your assets

```bash
yarn & yarn build
```

now if you check your home page you will get something like this

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/57tiy1f52bciut39u14q.png)

you can select from the top dropdown any section and add it to your page.

and you can build a menu from `/admin/menus` using this endpoint

* Home `/`
* About `/about`
* Shop `/shop`
* Blog `/blog`
* Contact `/contact`
* Terms & Conditions `/terms`
* Privacy `/privacy`

you can create 2 menus `main`, `footer` the main will show up auto to your header and the footer to your footer.

change the middleware of `Authenticate` redirecting to this route

```php
<?php

namespace App\Http\Middleware;

use Illuminate\Auth\Middleware\Authenticate as Middleware;
use Illuminate\Http\Request;

class Authenticate extends Middleware
{
    /**
     * Get the path the user should be redirected to when they are not authenticated.
     */
    protected function redirectTo(Request $request): ?string
    {
        return $request->expectsJson() ? null : route('accounts.login');
    }
}
```

now in your `Account.php` model add this trait

```php
    use \TomatoPHP\TomatoEcommerce\Services\Traits\InteractsWithEcommerce;
    use \TomatoPHP\TomatoNotifications\Traits\InteractWithNotifications;
    use \TomatoPHP\TomatoOrders\Services\Traits\InteractsWithOrders;
```

With the successful installation of our comprehensive E-commerce system, you are now equipped to seamlessly manage your product catalog. Begin by adding new products and defining categories to tailor your offerings. Feel empowered to kickstart the order creation process, as your E-commerce system stands ready to facilitate smooth transactions and streamline your online business operations.
