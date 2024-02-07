# 💿 Config

### GitHub Integration

to integrate and connect GitHub to your server you need to add this config to your `services.php` config

```php
'github' => [
    'client_id' => env('GITHUB_CLIENT_ID'),
    'client_secret' => env('GITHUB_CLIENT_SECRET'),
    'redirect' => 'https://example.com/admin/github/callback',
],
```

where `https://example.com` is your domain name and on your .env file change `GITHUB_CLIENT_ID`   `GITHUB_CLIENT_SECRET` with your own.

now you need to create a  new app on  your GitHub, The simplest way to create a GitHub app is to go to GitHub itself:

* Go to the `Settings` page of our profile.
* Go to `Developer Setting` from the left menu.
* Click on the `New GitHub App` button.

now your GitHub is connected and you can try to add new Credentials to GitHub.

### Integrate Cloudflare

you can integrate your Cloudflare to auto-add your subdomains to Cloudflare, by just adding these values

* Cloudflare ZONE ID \[The ZONE ID of your domain on Cloudflare]
* Cloudflare Email \[Your Cloudflare email]
* Cloudflare API Key \[Your Cloudflare API  Key With Zone Management Permissions]

### Change WebHook URL

we use webhook to interact with server tasks, so you need to make your URL online you can use services like Ngrok to share your local server to be online, or just upload your project and get a domain, then on your .env file add this var

```
WEBHOOK_URL=https://example.com
```

make sure that you add endpoint of the webhook to `VerifyCsrfToken` on `$except` array like this

```php
protected $except = [
    '/webhook/*',
];
```

### Publish Assets

you can publish a config file by using this command

```
php artisan vendor:publish --tag="tomato-eddy-config"
```

you can publish view files by using this command

```
php artisan vendor:publish --tag="tomato-eddy-views"
```

you can publish language files by using this command

```
php artisan vendor:publish --tag="tomato-eddy-lang"
```

you can publish migration files by using this command

```
php artisan vendor:publish --tag="tomato-eddy-migrations"
```
