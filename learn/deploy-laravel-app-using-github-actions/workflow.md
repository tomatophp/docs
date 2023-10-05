# 🎇 Workflow

the next step to build your CI/CD is to create a Workflow yaml file on your project repo, on your project file create a new folder with the name `.github` inside this folder create another one with the name `workflows` In this folder create a file with the name `ci.yaml`

```bash
mkdir .github
cd .github
mkdir workflows
cd workflows
touch ci.yaml
```

now on your yaml file add this script

```yaml
name: Testing Laravel with MySQL
on:
  pull_request:
    branches:
      - master
  push:
    branches:
      - master

jobs:
  laravel:
    name: Laravel (PHP ${{ matrix.php-versions }})
    runs-on: ubuntu-latest
    env:
      DB_DATABASE: laravel
      DB_USERNAME: root
      DB_PASSWORD: password
      BROADCAST_DRIVER: log
      CACHE_DRIVER: redis
      QUEUE_CONNECTION: redis
      SESSION_DRIVER: redis
    services:
      mysql:
        image: mysql:8.0
        env:
          MYSQL_ALLOW_EMPTY_PASSWORD: false
          MYSQL_ROOT_PASSWORD: password
          MYSQL_DATABASE: laravel
        ports:
          - 3306/tcp
        options: --health-cmd="mysqladmin ping" --health-interval=10s --health-timeout=5s --health-retries=3

      redis:
        image: redis
        ports:
          - 6379/tcp
        options: --health-cmd="redis-cli ping" --health-interval=10s --health-timeout=5s --health-retries=3
    strategy:
      fail-fast: false
      matrix:
        php-versions: ['8.2']
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup PHP
        uses: shivammathur/setup-php@v2
        with:
          php-version: ${{ matrix.php-versions }}
          extensions: sqlite, pdo_sqlite, pcntl, zip, intl, exif, mbstring, dom, fileinfo, mysql
          coverage: xdebug

      - name: Get composer cache directory
        id: composer-cache
        run: echo "dir=$(composer config cache-files-dir)" >> $GITHUB_OUTPUT

      - name: Cache composer dependencies
        uses: actions/cache@v3
        with:
          path: ${{ steps.composer-cache.outputs.dir }}
          # Use composer.json for key, if composer.lock is not committed.
          # key: ${{ runner.os }}-composer-${{ hashFiles('**/composer.json') }}
          key: ${{ runner.os }}-composer-${{ hashFiles('**/composer.lock') }}
          restore-keys: ${{ runner.os }}-composer-


      - name: Install Composer dependencies
        run: composer install --no-progress --prefer-dist --optimize-autoloader

      - name: Prepare Laravel Application
        run: |
          php -r "file_exists('.env') || copy('.env.example', '.env');"
          php artisan key:generate

      - name: Clear Config
        run: php artisan config:clear

      - name: Run Migration
        run: php artisan migrate -v
        env:
          DB_PORT: ${{ job.services.mysql.ports['3306'] }}
          REDIS_PORT: ${{ job.services.redis.ports['6379'] }}

      - name: Test with phpunit
        run: vendor/bin/phpunit --coverage-text
        env:
          DB_PORT: ${{ job.services.mysql.ports['3306'] }}
          REDIS_PORT: ${{ job.services.redis.ports['6379'] }}

      - name: Install Yarn dependencies
        run: yarn

      - name: Compile assets
        run: yarn build

      - name: Deploy to server
        uses: appleboy/ssh-action@master
        with:
          host: ${{ secrets.SSH_HOST }}
          username: ${{ secrets.SSH_USERNAME }}
          port: ${{ secrets.SSH_PORT }}
          password: ${{ secrets.SSH_PASSWORD }}
          script: cd ${{ secrets.SSH_PATH }} && ./.scripts/deploy.sh
```

this script takes fire when any push comes to `master` branch, and after testing everything on your app it will run the Script using SSH on your server by using details on the server on GitHub Secrets to change these details go to your GitHub repo and then the Settings tab, and then select Actions secrets and variables and then add a new secret with key `SSH_HOST` with your server IP, and you must add details like this

```bash
SSH_HOST: 8.8.8.8
SSH_USERNAME: yourproject
SSH_PORT: 22
SSH_PASSWORD: yourpassword
SSH_PATH: /home/yourproject/htdocs/yourdomain.com
```

then make sure you change these details on `.env.example`

```bash
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=password
```

now it's time to create a Deploy Script on the next step
