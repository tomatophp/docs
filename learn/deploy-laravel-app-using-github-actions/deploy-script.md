# 🦕 Deploy Script

the deploy script is the script that runs every time you make a push, so you must add a selected command when it runs every time you make a push.

to add a script make a folder with the name .scripts and then create a file deploy.sh and make sure you give the file permissions to run with 755.

```bash
mkdir .scripts
cd .scripts
touch script.sh
chmod 755 deploy.sh
```

now your deploy script is ready add to this file this script and you can custom it as you like

```bash
#!/bin/bash
set -e

echo "Deployment started ..."

# Enter maintenance mode or return true
# if already is in maintenance mode
(php artisan down) || true

# Pull the latest version of the app
git reset --hard
git pull origin master

# Install composer dependencies
composer install --no-dev --no-interaction --prefer-dist --optimize-autoloader

# Clear the old cache
php artisan clear-compiled

# Recreate cache
php artisan optimize

# Compile npm assets
yarn
yarn build

# Run database migrations
php artisan migrate --force

# Exit maintenance mode
php artisan up

echo "Deployment finished!"

```

now push all of these updates to your GitHub repo and you will find on the Actions tab that the action is run and after that, you will find the updates on your server.
