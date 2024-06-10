# 🛁 Auth Events

we have added a lot of events to the package, so you can listen to them and do what you want.

#### OTP Event

```php
use TomatoPHP\FilamentAccounts\Events\SendOTP;
use TomatoPHP\FilamentAlerts\Services\SendNotification;

public function register()
{
    Event::listen([
        SendOTP::class
    ], function ($data) {
        $user = $data->model::find($data->modelId);

        SendNotification::make(['email'])
            ->title('OTP')
            ->message('Your OTP is ' . $user->otp_code)
            ->type('info')
            ->database(false)
            ->model(Account::class)
            ->id($user->id)
            ->privacy('private')
            ->icon('bx bx-user')
            ->url(url('/'))
            ->fire();
    });
}
```

#### Account Success Login Event

When the user logs in successfully, we fire this event.

```php
use TomatoPHP\FilamentAccounts\Events\AccountLogged;

public function register()
{
    Event::listen([
        AccountLogged::class
    ], function ($data) {
        $user = $data->model::find($data->modelId);
        if($user->meta('is_admin_approve') !== 'yes'){
            return response()->json([
                "status" => false,
                "message" => __('your Account is activated. but you cannot login till admin approve.'),
            ], 400)->send();
        }
    });
}
```

#### Account Registered Event

When the user registers successfully, we fire this event.

```php
use TomatoPHP\FilamentAccounts\Events\AccountLogged;

public function register()
{
    Event::listen([
        AccountRegistered::class
    ], function ($data) {
        $user = $data->model::find($data->modelId);
        $user->last_login = Carbon::now();
        $user->save();
    });
}
```
