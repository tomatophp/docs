# ✨ Start Your First CRUD

you can build a CRUD after you make a migration for your table, let's say you need to build a customer's table through this migration.

you can create a new migration

```bash
php artisan make:migration create_customers_table
```

and after that, you can build your customer table schema.

```php

<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

class CreateCustomersTable extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('customers', function (Blueprint $table) {
            $table->id();
            $table->string('name')->index();
            $table->longText('bio')->nullable();
            $table->string('email')->unique()->index();
            $table->string('phone');
            $table->text('address')->nullable();
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('customers');
    }
}
```

run migration to create the table

```bash
php artisan migrate
```

now you need to install our Generator Plugin Tomato PHP so please use this command to install it

```bash
composer require tomatophp/tomato-php
```

and here is the tomato step just use this command

```bash
php artisan tomato:generate
```

it will ask you about the table name you generate a migration for it, and if you like to use Laravel Modules, you can just say `y` on the next ask.

now you need to add a menu item to the `AppServiceProvier boot()` function like this

```php
use TomatoPHP\TomatoAdmin\Facade\TomatoMenu;
use TomatoPHP\TomatoAdmin\Services\Contracts\Menu;

... 

public function boot()
{
    TomatoMenu::register(
        Menu::make()
            ->group('Resources')
            ->label('Users')
            ->route('admin.users.index')
            ->icon('bx bx-user')
    );
}
```

This facade accepts an array or just 1 Menu class so you can use it as you like

make sure that your view is clean by using this command

```bash
php aritsan optimize:clear
```

BOM.. your CRUD is ready.
