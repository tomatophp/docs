# 🎹 Use

it's straightforward to use our package by just creating a new migration and migrating it after your table and schema are ready to use this command

```
php artisan tomato:generate
```

it will ask you to input the table name and bingo you get the full CRUD ready.

### What is the file we are generating?

you build a full CRUD with some files like

* Controller \[app\Http\Controllers\Admin]
* Table \[app\Tables]
* Model \[app\Models]
* Views \[resources\views\admin\TABLE]
* Routes \[routes\web.php]