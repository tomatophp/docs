# ⏯️ Usage

this plugin makes it easy to make a starting point for your app if this app has customers to manage

but here is the problem, every app has a different way of managing customers, so we built a Facade service to control the way you want to manage your customers

You can build multi-auth using the same accounts table in a very easy way, so we created a Facade class to help you do that.

#### How to use

you just need to create 2 controllers `AuthController`, `ProfileController`

```php
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Login;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Register;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Otp;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\ResetPassword;

class AuthController extends Controller
{
    use Login;
    use Register;
    use Otp;
    use ResetPassword;
    
    public string $guard = 'web';
    public bool $otp = true;
    public string $model = Account::class;
    public string $loginBy = 'email';
    public string $loginType = 'email';
    public ?string $resource = null;

    public function __construct()
    {
        $this->guard = config('filament-accounts.guard');
        $this->otp = config('filament-accounts.required_otp');
        $this->model = config('filament-accounts.model');
        $this->loginBy = config('filament-accounts.login_by');
        $this->loginType = config('filament-accounts.login_by');
        $this->resource = config('filament-accounts.resource', null);
    }
```

and on your profile controller, you just need to use `Profile` traits

```php
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Profile\User;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Profile\Update;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Profile\Delete;
use TomatoPHP\FilamentAccounts\Services\Traits\Auth\Profile\Logout;

class ProfileController extends Controller
{
    use User;
    use Update;
    use Delete;
    use Logout;

    public string $guard = 'web';
    public bool $otp = true;
    public string $model = Account::class;
    public string $loginBy = 'email';
    public string $loginType = 'email';
    public ?string $resource = null;

    public function __construct()
    {
        $this->guard = config('filament-accounts.guard');
        $this->otp = config('filament-accounts.required_otp');
        $this->model = config('filament-accounts.model');
        $this->loginBy = config('filament-accounts.login_by');
        $this->loginType = config('filament-accounts.login_by');
        $this->resource = config('filament-accounts.resource', null);
    }
}
```
