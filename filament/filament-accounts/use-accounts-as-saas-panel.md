# 🎇 Use Accounts as SaaS Panel

[![Register](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/register.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/register.png) [![OTP](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/otp.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/otp.png) [![Panel Home](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/panel-home.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/panel-home.png) [![Panel Menu](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/panel-menu.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/panel-menu.png) [![Edit Profile](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/edit-profile.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/edit-profile.png) [![Manage Sessions](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/manage-sessions.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/manage-sessions.png) [![Team Settings](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/team-settings.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/team-settings.png) [![Invite Team](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/invite-team.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/invite-team.png) [![API Tokens](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/api-tokens.png)](https://raw.githubusercontent.com/tomatophp/filament-accounts/master/arts/api-tokens.png)

Install Jetstream without installing it.

```
composer require laravel/jetstream
```

on your new panel just use this plugin

```php
->plugin(
    FilamentAccountsSaaSPlugin::make()
        ->databaseNotifications()
        ->checkAccountStatusInLogin()
        ->APITokenManager()
        ->editTeam()
        ->deleteTeam()
        ->teamInvitation()
        ->showTeamMembers()
        ->editProfile()
        ->editPassword()
        ->browserSesstionManager()
        ->deleteAccount()
        ->editProfileMenu()
        ->registration()
        ->useOTPActivation(),
)
```

you can change settings by removing just methods from the plugin.
