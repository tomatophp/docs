# 🎹 Use

it's straightforward to use our package by just creating a new migration and migrating it after your table and schema are ready to use this command

```
php artisan tomato:generate
```

it will ask you to input the table name and bingo you get the full CRUD ready.

### What is the file we are generating?

you build a full CRUD with some files like

* Controller \[app\Http\Controllers\Admin]
* Model \[app\Models]
* Requests \[app\Http\Requests\TABLE]
* Views \[resources\views\admin\TABLE]
* Routes \[routes\web.php]

### Tomato Helper

you can use `Tomato::class` helper on your controller or override it&#x20;

if you went to use [Laravel-medialibrary](https://spatie.be/docs/laravel-medialibrary/v10/introduction) with a helper you could do that

```php
$data = Tomato::store(
    request: $request,
    model: \App\Models\Customer::class,
    message: 'Customer created successfully',
    redirect: 'customers.index',
    hasMedia: true,
    collection: "photos",
    multi: true
);
```

as you see you can use&#x20;

`hasMedia` to make the helper accept media and use&#x20;

`collection` to set the collection name and use&#x20;

`multi` to allow it to accept multi files
