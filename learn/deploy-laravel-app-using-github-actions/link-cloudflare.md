# 🔓 Link Cloudflare

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

we believe that the security and cache are better for any app, so we need to secure our server by using Cloudflare DNS reverser and its power of caching.

### Create Cloudflare account

it's easy to create a new Cloudflare account like any website out to this [link](https://dash.cloudflare.com/sign-up) and create a new account

### Add your domain to Cloudflare

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

to add your domain to Cloudflare, on the dashboard of Cloudflare you will find the Websites tab you can click on it and click on the right button to Add a site

after that I will ask you to add your domain and give you a namespace to change it on your domain then go to your domain service provider and change the namespace to the Cloudflare namespace, this process can take 24 hours for some providers, I use Google Domains it takes just 10min, and now your domain is ready on the Cloudflare.

### Connect Domain to Cloudpanel

now get to your domain after activating it, you will find the DNS tab click on it and add a new `A Record` with your `server IP` **make sure that your Proxy status is DNS only** and that can be pointed to `cp.`&#x20;

now go to your Cloudpanel click on Admin Area and then select Settings and change CloudPanel Custom Domain to `cp.YOUR_DOMAIN`&#x20;

it will generate auto SSL for you and link the domain for you, you can access the Cloudpanel using your domain

### Connect Project Domain

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

to connect your project domain you need to add a new website, from the Website tab click on the Add Site button, select Create PHP Site App, fill in the details, and click on Create.

now Cloudpanel will redirect and add an nginx template and PHP-FPM to point your domain, go to Cloudflare and add a new DNS A Record and point it to your server domain, then go to SSL/TLS tab and create a new Origin Server SSL, it will give you a 15 years SSL for free, copy it and go to Cloudpanel and select your new Website app and from the tab of SSL/TLS Click on actions and then Import Certificate and add the Cloudflare SSL.

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

now your domain is linked and secured by SSL, you can access your domain with SSL and make sure that the domain is working.

