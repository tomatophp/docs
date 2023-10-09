# 📐 Use

it's very easy to use just use this command

```
php artisan tomato:test
```

it will ask you about the test case name and it will generate a test class on the path `tests/Browser/Tomato`

after you generate it you can add your code and after that register the class on the `tomato-dusk.php` config file and run

```
php artisan config:cache
```

you now can run your test cases by GUI or this command

```
php artisan tomato-dusk:run
```
