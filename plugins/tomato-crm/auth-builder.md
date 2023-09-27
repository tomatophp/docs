# 🏗 Auth Builder

you can build multi-auth using the same accounts table in a very easy way, so we created a Facade class to help you do that.

### How to use

you just need to create 2 controllers `AuthController`, `ProfileController`

```php

use TomatoPHP\TomatoCrm\Services\Traits\Auth\Login;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Register;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Otp;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\ResetPassword;

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
        $this->guard = config('tomato-crm.guard');
        $this->otp = config('tomato-crm.required_otp');
        $this->model = config('tomato-crm.model');
        $this->loginBy = config('tomato-crm.login_by');
        $this->loginType = config('tomato-crm.login_by');
        $this->resource = config('tomato-crm.resource', null);
    }
```

and on your profile controller, you just need to use `Profile` traits

```php
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Profile\User;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Profile\Update;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Profile\Delete;
use TomatoPHP\TomatoCrm\Services\Traits\Auth\Profile\Logout;

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
        $this->guard = config('tomato-crm.guard');
        $this->otp = config('tomato-crm.required_otp');
        $this->model = config('tomato-crm.model');
        $this->loginBy = config('tomato-crm.login_by');
        $this->loginType = config('tomato-crm.login_by');
        $this->resource = config('tomato-crm.resource', null);
    }
}
```
